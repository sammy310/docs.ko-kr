---
title: "'<attributename>' 특성을 여러 번 사용할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: f2f4dc428a247275f9919c4a8b6e6944a558eef0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968233"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a>'\<attributename > ' 특성을 여러 번 적용할 수 없습니다.

특성은 한 번만 적용할 수 있습니다. `AttributeUsage` 특성은 특성을 두 번 이상 적용할 수 있는지 여부를 결정 합니다.  
  
 **오류 ID:** BC30663  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 특성이 한 번만 적용 되는지 확인 합니다.  
  
2. 개발한 사용자 지정 특성을 사용 하는 경우 다음 예제와 같이 `AttributeUsage` 특성을 변경 하 여 여러 특성 사용을 허용 하는 것이 좋습니다.  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>참조

- <xref:System.AttributeUsageAttribute>
- [사용자 지정 특성 만들기](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [AttributeUsage](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
