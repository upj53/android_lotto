# 안드로이드 스튜디오로 개발한 로또 번호 생성기 앱

![실행화면](/images/lotto_1.png)    
로또 번호 생성기 앱 실행화면

```kotlin
  // 로또 번호를 중복을 허용하고 생성하는 함수
	private fun getLottoNumber1() {
		val rnd = Random()
		val lotto = IntArray(6)
		for (i in lotto.indices) {
			lotto[i] = rnd.nextInt(45) + 1
		}
		lotto.sort()
		setTvNumber(lotto[0], binding.tvLotto1)
		setTvNumber(lotto[1], binding.tvLotto2)
		setTvNumber(lotto[2], binding.tvLotto3)
		setTvNumber(lotto[3], binding.tvLotto4)
		setTvNumber(lotto[4], binding.tvLotto5)
		setTvNumber(lotto[5], binding.tvLotto6)
	}
```

```kotlin
  // 로또 번호를 중복을 허용하지 않고 생성하는 함수
	private fun getLottoNumber2() {
		val rnd = Random()
		val lotto = IntArray(6)
		while (true) {
			var isSame = false
			for (i in lotto.indices) {
				lotto[i] = rnd.nextInt(45) + 1
			}
			for (i in lotto.indices) {
				for (j in lotto.indices) {
					if (i != j) {
						if (lotto[i] == lotto[j]) {
							isSame = true
						}
					}
				}
			}
			if (!isSame) {
				break
			}
		}
		lotto.sort()
		setTvNumber(lotto[0], binding.tvLotto1)
		setTvNumber(lotto[1], binding.tvLotto2)
		setTvNumber(lotto[2], binding.tvLotto3)
		setTvNumber(lotto[3], binding.tvLotto4)
		setTvNumber(lotto[4], binding.tvLotto5)
		setTvNumber(lotto[5], binding.tvLotto6)
	}
```
