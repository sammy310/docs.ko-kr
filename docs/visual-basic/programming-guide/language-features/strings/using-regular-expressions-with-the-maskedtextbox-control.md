---
title: MaskedTextBox 컨트롤과 함께 정규식 사용
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], regular expressions
- strings [Visual Basic], masked edit
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
ms.openlocfilehash: efda70be0ccdbc1f4b59d548e50f743f6c493b19
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363717"
---
# <a name="using-regular-expressions-with-the-maskedtextbox-control-in-visual-basic"></a>Visual Basic에서 MaskedTextBox 컨트롤과 함께 정규식 사용
이 예제에서는 간단한 정규식을 컨트롤에서 사용할 수 있도록 변환 하는 방법을 보여 줍니다 <xref:System.Windows.Forms.MaskedTextBox> .  
  
## <a name="description-of-the-masking-language"></a>마스킹 언어 설명  
 표준 <xref:System.Windows.Forms.MaskedTextBox> 마스킹 언어는 Visual Basic 6.0의 컨트롤에서 사용 하는 언어를 기반으로 `Masked Edit` 하며 해당 플랫폼에서 마이그레이션하는 사용자에 게 익숙할 것입니다.  
  
 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>컨트롤의 속성은 <xref:System.Windows.Forms.MaskedTextBox> 사용할 입력 마스크를 지정 합니다. 마스크는 다음 표의 마스킹 요소 중 하나 이상으로 구성 된 문자열 이어야 합니다.  
  
|마스킹 요소|Description|Regular expression 요소|  
|---------------------|-----------------|--------------------------------|  
|0|0에서 9 사이의 단일 숫자입니다. 항목이 필요 합니다.|\d|  
|9|숫자 또는 공간. 항목을 선택 합니다.|[\d]?|  
|#|숫자 또는 공간. 항목을 선택 합니다. 마스크에서이 위치를 비워 두면 공백으로 렌더링 됩니다. 더하기 (+) 및 빼기 (-) 기호가 허용 됩니다.|[\d +-]?|  
|L|ASCII 문자입니다. 항목이 필요 합니다.|[a-zA-Z]|  
|?|ASCII 문자입니다. 항목을 선택 합니다.|[a-zA-Z]?|  
|&|문자. 항목이 필요 합니다.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]|  
|C|문자. 항목을 선택 합니다.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]?|  
|A|영숫자만. 항목을 선택 합니다.|\W|  
|.|문화권에 맞는 소수 자리 표시자입니다.|사용할 수 없습니다.|  
|,|문화권에 따라 적절 한 천 단위 자리 표시자입니다.|사용할 수 없습니다.|  
|:|문화권에 맞는 시간 구분 기호입니다.|사용할 수 없습니다.|  
|/|문화권에 따라 적절 한 날짜 구분 기호입니다.|사용할 수 없습니다.|  
|$|문화권에 맞는 통화 기호입니다.|사용할 수 없습니다.|  
|\<|뒤에 오는 모든 문자를 소문자로 변환 합니다.|사용할 수 없습니다.|  
|>|뒤에 오는 모든 문자를 대문자로 변환 합니다.|사용할 수 없습니다.|  
|&#124;|이전 shift 키를 실행 취소 합니다.|사용할 수 없습니다.|  
|&#92;|마스크 문자를 이스케이프 하 여 리터럴로 변환 합니다. " \\ \\ "는 백슬래시의 이스케이프 시퀀스입니다.|&#92;|  
|기타 모든 문자입니다.|리터럴. 모든 비 마스크 요소는 내에 자체 표시 됩니다 <xref:System.Windows.Forms.MaskedTextBox> .|기타 모든 문자입니다.|  
  
 소수점 (.), 1/1000 (,), 시간 (:), (/), 날짜 및 통화 ($) 기호 기본 애플리케이션의 문화권에서 정의 된 대로 해당 기호를 표시 합니다. 속성을 사용 하 여 다른 문화권의 기호를 표시 하도록 강제할 수 있습니다 <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A> .  
  
## <a name="regular-expressions-and-masks"></a>정규식 및 마스크  
 정규식과 마스크를 사용 하 여 사용자 입력의 유효성을 검사할 수 있지만 완전히 일치 하지는 않습니다. 정규식은 마스크 보다 더 복잡 한 패턴을 표현할 수 있지만 마스크는 간략하게 및 문화권 관련 형식으로 동일한 정보를 표현할 수 있습니다.  
  
 다음 표에서는 정규식 4 개와 각 정규식에 해당 하는 마스크를 비교 합니다.  
  
|정규식|Mask|메모|  
|------------------------|----------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|`/`마스크의 문자는 논리적 날짜 구분 기호 이며, 사용자에 게 응용 프로그램의 현재 문화권에 적절 한 날짜 구분 기호로 표시 됩니다.|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|미국 형식으로 된 날짜 (일, 월 약어 및 연도)로, 세 문자 월 약어가 앞에 대문자를 표시 하 고 두 개의 소문자를 표시 합니다.|  
|`(\(\d{3}\)-)?\d{3}-d{4}`|`(999)-000-0000`|미국 전화 번호, 지역 번호 (선택 사항). 사용자가 선택적 문자를 입력 하지 않으려는 경우 공백을 입력 하거나 처음 0으로 표시 되는 마스크의 위치에 직접 마우스 포인터를 놓을 수 있습니다.|  
|`$\d{6}.00`|`$999,999.00`|0 ~ 999999 범위의 통화 값입니다. 통화, 1000, 10 진수 문자는 런타임에 해당 하는 문화권 관련 항목으로 바뀝니다.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>
- <xref:System.Windows.Forms.MaskedTextBox>
- [Visual Basic의 문자열 유효성 검사](validating-strings.md)
- [MaskedTextBox 컨트롤](../../../../framework/winforms/controls/maskedtextbox-control-windows-forms.md)
