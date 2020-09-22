---
title: <exception>
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: e3f386d2a1e15ea3e1519d6e1e5e31c34c73fb99
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872901"
---
# <a name="exception-visual-basic"></a>\<exception>(Visual Basic)

Throw 할 수 있는 예외를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a>매개 변수  

 `member`  
 현재 컴파일 환경에서 사용할 수 있는 예외에 대한 참조입니다. 컴파일러는 지정된 예외가 있으며 `member`를 출력 XML의 정식 요소 이름으로 변환하는지 확인합니다. `member`는 큰따옴표(" ")로 묶어야 합니다.  
  
 `description`  
 설명  
  
## <a name="remarks"></a>설명  

 태그를 사용 `<exception>` 하 여 throw 할 수 있는 예외를 지정 합니다. 이 태그는 메서드 정의에 적용됩니다.  
  
 [-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  

 이 예제에서는 태그를 사용 하 여 `<exception>` `IntDivide` 함수가 throw 할 수 있는 예외를 설명 합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>참조

- [XML 주석 태그](index.md)
