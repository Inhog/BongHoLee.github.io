---
layout: post
title: 깃헙 페이지 업로드 오류
author: Bong5
category:
  - LearnFromSapzil
summary: 깃헙 페이지 수정 후 적용 안되는 오류
thumbnail: posts/hello.jpg
---

## 깃헙 페이지 오류
---
깃헙 페이지를 활용하여 블로그를 개설한지 약 __세 시간__ 만에 난항에 부딪혔다.

지킬 테마를 clone, customize, commit, push를 몇 번 했지만 어느 순간부터 깃헙 페이지에 적용이 안되는 현상.

처음에는 아직 반영이 안되었다고 생각하여 주구장창(24시간 가량..) 기다렸건만 변하는건 없었다.

결과적으로 <s>업무시간까지 할애해 가며</s> 깃헙 페이지를 삭제하고 재등록하고.. 무엇이 문제인지 _posts를 비롯한 많은 파일과 디렉토리들을 제거한 뒤에야 찾아냈다.

뭐.. 결과적으로는 _config.yml 파일에 문법(구문)오류가 있었던게 문제였는데. 아무래도 commit, push를 하는 과정에서는
에러 로그 등을 파악하지 못하기 때문에 깃헙에서 자체적으로 반영을 시키지 않아준 것 같다(이것 또 꺠달았습니다..)

이를 방지하기 위하여 로컬에서 jekyll 서버를 구동하여 테스트 함으로써 에러 발생시 로그를 확인하는 방향으로 진행해야 겠다.
