---
title: MaskedTextBox 컨트롤과 함께 정규식 사용
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], regular expressions
- strings [Visual Basic], masked edit
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
ms.openlocfilehash: b997f6f495fca51e888bb995fee0361d29d68048
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148286"
---
# <a name="using-regular-expressions-with-the-maskedtextbox-control-in-visual-basic"></a>Visual Basic에서 MaskedTextBox 컨트롤과 함께 정규식 사용
이 예제에서는 컨트롤에서 작동 하도록 간단한 정규식을 변환 하는 <xref:System.Windows.Forms.MaskedTextBox> 방법을 보여 줍니다.  
  
## <a name="description-of-the-masking-language"></a>마스킹 언어에 대한 설명  
 표준 <xref:System.Windows.Forms.MaskedTextBox> 마스킹 언어는 Visual Basic 6.0의 `Masked Edit` 컨트롤에서 사용하는 언어를 기반으로 하며 해당 플랫폼에서 마이그레이션하는 사용자에게 익숙해야 합니다.  
  
 <xref:System.Windows.Forms.MaskedTextBox> 컨트롤의 속성은 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 사용할 입력 마스크를 지정합니다. 마스크는 다음 표에서 하나 이상의 마스킹 요소로 구성된 문자열이어야 합니다.  
  
|마스킹 요소|Description|정규 표현식 요소|  
|---------------------|-----------------|--------------------------------|  
|0|0에서 9 사이의 모든 단일 숫자. 입국이 필요합니다.|\d|  
|9|숫자 또는 공간입니다. 항목 선택 사항입니다.|[ \d]?|  
|#|숫자 또는 공간입니다. 항목 선택 사항입니다. 이 위치가 마스크에 비어 있으면 공백으로 렌더링됩니다. 플러스 (+) 및 마이너스 (-) 기호가 허용됩니다.|[ \d +-]?|  
|L|ASCII 편지. 입국이 필요합니다.|[a-zA-Z]|  
|?|ASCII 편지. 항목 선택 사항입니다.|[a-zA-Z]?|  
|&|문자. 입국이 필요합니다.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]|  
|C|문자. 항목 선택 사항입니다.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}?|  
|A|영숫자. 항목 선택 사항입니다.|\W|  
|.|문화권에 적합한 소수자릿수 자리 표시자입니다.|사용할 수 없습니다.|  
|,|문화권에 적합한 수천 자리 표시자입니다.|사용할 수 없습니다.|  
|:|문화적 시간 구분 기호입니다.|사용할 수 없습니다.|  
|/|문화적절한 날짜 구분 기호입니다.|사용할 수 없습니다.|  
|$|문화에 적합한 통화 기호입니다.|사용할 수 없습니다.|  
|\<|다음에 있는 모든 문자를 소문자로 변환합니다.|사용할 수 없습니다.|  
|>|다음에 있는 모든 문자를 대문자로 변환합니다.|사용할 수 없습니다.|  
|&#124;|이전 시프트를 위로 또는 아래로 이동 취소합니다.|사용할 수 없습니다.|  
|&#92;|마스크 문자를 이스케이프하여 리터럴로 바꿔보릅니다. "\\\\백슬래시의 이스케이프 시퀀스입니다.|&#92;|  
|다른 모든 문자.|리터럴. 마스크가 아닌 모든 요소는 에 <xref:System.Windows.Forms.MaskedTextBox>있는 자체로 표시됩니다.|다른 모든 문자.|  
  
 소수점 (.), 1/1000 (,), 시간 (:), (/), 날짜 및 통화 ($) 기호 기본 애플리케이션의 문화권에서 정의 된 대로 해당 기호를 표시 합니다. <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A> 속성을 사용하여 다른 문화기호에 대한 기호를 표시하도록 강제할 수 있습니다.  
  
## <a name="regular-expressions-and-masks"></a>정규 표현식 및 마스크  
 정규식과 마스크를 사용하여 사용자 입력의 유효성을 검사할 수 있지만 완전히 동일하지는 않습니다. 정규표현식은 마스크보다 더 복잡한 패턴을 표현할 수 있지만 마스크는 동일한 정보를 더 간결하고 문화적으로 관련된 형식으로 표현할 수 있습니다.  
  
 다음 표는 네 개의 정규식과 각각에 해당하는 마스크를 비교합니다.  
  
|정규식|Mask|메모|  
|------------------------|----------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|마스크의 문자는 `/` 논리적 날짜 구분 기호이며 응용 프로그램의 현재 문화권에 적합한 날짜 구분 기호로 사용자에게 표시됩니다.|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|세 글자 달 약어가 초기 대문자 문자뒤에 두 개의 소문자 문자와 함께 표시되는 미국 형식의 날짜(일, 월 약어 및 연도)입니다.|  
|`(\(\d{3}\)-)?\d{3}-d{4}`|`(999)-000-0000`|미국 전화 번호, 지역 번호 선택 사항. 사용자가 선택적 문자를 입력하지 않으려면 공백을 입력하거나 마우스 포인터를 처음 0으로 표시된 마스크의 위치에 직접 배치할 수 있습니다.|  
|`$\d{6}.00`|`$999,999.00`|0에서 999999 범위의 통화 값입니다. 통화, 천번째 및 소수 문자는 런타임에 해당 문화부별 등가물로 대체됩니다.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>
- <xref:System.Windows.Forms.MaskedTextBox>
- [Visual Basic의 문자열 유효성 검사](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
- [MaskedTextBox 컨트롤](../../../../framework/winforms/controls/maskedtextbox-control-windows-forms.md)
