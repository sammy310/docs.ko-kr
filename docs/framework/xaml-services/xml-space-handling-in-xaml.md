---
title: XAML의 xml:space 처리
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 8f860f5ee42b5c1df43c4ec2b1003408bc1c0d8e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458799"
---
# <a name="xmlspace-handling-in-xaml"></a>XAML의 xml:space 처리
`xml:space` 특성은 개체 요소 내에서 중요 한 공백 처리 동작을 선언 하는 XML로 정의 된 특성입니다. 이 동작은 `xml:space` 선언 된 요소 내에 포함 된 모든 콘텐츠 (내부 텍스트)와 관련 되 고 자식 요소에도 범위를 적용 합니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 \- 또는 -  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a>주의  
 두 가지 가능한 값을 포함 하 여 XAML의 `xml:space` 특성에 대 한 정의는 W3C 사양에 따라 XML에 대해 "특수 특성"으로 정의 된 `xml:space`에서 파생 됩니다.  
  
 `xml:space` 특성의 기본값은 `"default"`리터럴 값입니다. 값 `"default"`의 경우 또는 `xml:space` 표시 되지 않는 경우에는 [XAML의 공백 처리](whitespace-processing-in-xaml.md)항목에 정의 된 대로 중요 한 공백 구문 분석 동작이 기본 처리입니다.  
  
 개체 요소 내용 내에서 공백을 유지 하려면 해당 개체 요소에 `xml:space="preserve"`를 지정 합니다.  
  
 대부분의 해석에서 특성의 영향을 `xml:space` 특성의 값은 자식 요소로 범위가 지정 됩니다.  
  
 XAML의 공백 처리에 대 한 자세한 내용은 [xaml의 공백 처리](whitespace-processing-in-xaml.md)를 참조 하세요.  
  
## <a name="see-also"></a>참조

- [XAML의 공백 처리](whitespace-processing-in-xaml.md)
- [XAML 개요(WPF)](../../desktop-wpf/fundamentals/xaml.md)
