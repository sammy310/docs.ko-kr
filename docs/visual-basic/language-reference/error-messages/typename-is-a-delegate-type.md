---
title: "'<typename>'은(는) 대리자 형식입니다."
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 7056bbf2b4de26feba3bfbe0e02b3239311271c9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84382174"
---
# <a name="typename-is-a-delegate-type"></a>'\<typename>'은(는) 대리자 형식입니다.
' \<typename> '은 (는) 대리자 형식입니다. 대리자 생성은 단일 AddressOf 식만 인수 목록으로 허용 합니다. 일반적으로 대리자 생성 대신 AddressOf 식을 사용할 수 있습니다.  
  
 `New`대리자 클래스의 인스턴스를 만드는 절은 대리자 생성자에 잘못 된 인수 목록을 제공 합니다.  
  
 `AddressOf`새 대리자 인스턴스를 만들 때 단일 식만 제공할 수 있습니다.  
  
 이 오류는 대리자 생성자에 인수를 전달 하지 않거나 둘 이상의 인수를 전달 하거나 유효한 식이 아닌 단일 인수를 전달 하는 경우에 발생할 수 있습니다 `AddressOf` .  
  
 **오류 ID:** BC32008  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- `AddressOf`절에서 대리자 클래스의 인수 목록에 있는 단일 식을 사용 `New` 합니다.  
  
## <a name="see-also"></a>참고 항목

- [새 운영자](../operators/new-operator.md)
- [AddressOf 연산자](../operators/addressof-operator.md)
- [대리자](../../programming-guide/language-features/delegates/index.md)
- [방법: 대리자 메서드 호출](../../programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
