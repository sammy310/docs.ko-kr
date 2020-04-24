---
title: 사용자 입력 유효성 검사
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, validating user input
- validation [Windows Forms], Windows Forms user input
- user input [Windows Forms], validating in Windows Forms
- validating user input [Windows Forms], Windows Forms
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
ms.openlocfilehash: eafbf54552566011fef9d2dbeb5e9f9fa3facabd
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646297"
---
# <a name="user-input-validation-in-windows-forms"></a>Windows Forms에서 사용자 입력 유효성 검사
사용자가 응용 프로그램에 데이터를 입력할 때 응용 프로그램에서 데이터를 사용하기 전에 데이터가 유효한지 확인할 수 있습니다. 특정 텍스트 필드가 0길이가 아니거나, 필드가 전화 번호 또는 다른 형식의 데이터 로 서식을 지정하거나, 데이터베이스 보안을 손상시키는 데 사용할 수 있는 안전하지 않은 문자가 문자열에 포함되지 않도록 요구할 수 있습니다. Windows Forms는 응용 프로그램의 입력 유효성을 검사하는 여러 가지 방법을 제공합니다.  
  
## <a name="validation-with-the-maskedtextbox-control"></a>마스크된 텍스트 상자 컨트롤을 통한 유효성 검사  
 사용자가 전화 번호 나 부품 번호와 같이 잘 정의 된 형식으로 데이터를 입력하도록 요구하는 경우 컨트롤을 <xref:System.Windows.Forms.MaskedTextBox> 사용하여 최소한의 코드로 이 작업을 신속하게 수행 할 수 있습니다. *마스크는* 텍스트 상자의 지정된 위치에서 입력할 수 있는 문자를 지정하는 마스킹 언어의 문자로 구성된 문자열입니다. 컨트롤은 사용자에게 프롬프트 집합을 표시합니다. 예를 들어 사용자가 잘못된 항목을 입력하는 경우(예: 숫자가 필요할 때 사용자가 문자를 입력하면 컨트롤이 자동으로 입력을 거부합니다.)  
  
 사용되는 마스킹 <xref:System.Windows.Forms.MaskedTextBox> 언어는 매우 유연합니다. 필요한 문자, 선택적 문자, 하이픈 및 괄호, 통화 문자 및 날짜 구분 기호와 같은 리터럴 문자를 지정할 수 있습니다. 컨트롤은 데이터 원본에 바인딩할 때도 잘 작동합니다. 데이터 <xref:System.Windows.Forms.Binding.Format> 바인딩의 이벤트는 마스크를 준수하기 위해 들어오는 데이터를 다시 포진하는 <xref:System.Windows.Forms.Binding.Parse> 데 사용할 수 있으며, 이벤트는 데이터 필드의 사양을 준수하기 위해 나가는 데이터를 다시 포진하는 데 사용할 수 있습니다.  
  
 자세한 내용은 [마스크된 텍스트 상자 컨트롤](./controls/maskedtextbox-control-windows-forms.md)을 참조하십시오.  
  
## <a name="event-driven-validation"></a>이벤트 기반 유효성 검사  
 유효성 검사에 대한 전체 프로그래밍 방식으로 제어하거나 복잡한 유효성 검사를 수행해야 하는 경우 대부분의 Windows Forms 컨트롤에 기본 제공된 유효성 검사 이벤트를 사용해야 합니다. 자유 형식 사용자 입력을 허용하는 각 <xref:System.Windows.Forms.Control.Validating> 컨트롤에는 컨트롤에 데이터 유효성 검사가 필요할 때마다 발생하는 이벤트가 있습니다. 이벤트 <xref:System.Windows.Forms.Control.Validating> 처리 메서드에서 여러 가지 방법으로 사용자 입력의 유효성을 검사할 수 있습니다. 예를 들어 우편 번호를 포함해야 하는 텍스트 상자가 있는 경우 다음과 같은 방법으로 유효성 검사를 수행할 수 있습니다.  
  
- 우편 번호가 특정 우편 번호 그룹에 속해야 하는 경우 입력에서 문자열 비교를 수행하여 사용자가 입력한 데이터의 유효성을 검사할 수 있습니다. 예를 들어 우편 번호가 {10001, 10002, 10003}집합에 있어야 하는 경우 문자열 비교를 사용하여 데이터의 유효성을 검사할 수 있습니다.  
  
- 우편 번호가 특정 양식에 있어야 하는 경우 정규식을 사용하여 사용자가 입력한 데이터의 유효성을 검사할 수 있습니다. 예를 들어 폼의 `#####` 유효성을 검사하거나 `#####-####`정규식을 `^(\d{5})(-\d{4})?$`사용할 수 있습니다. 폼의 `A#A #A#`유효성을 검사하려면 정규식을 `[A-Z]\d[A-Z] \d[A-Z]\d`사용할 수 있습니다. 정규식에 대한 자세한 내용은 [.NET Framework 정규식](../../standard/base-types/regular-expressions.md) 및 [정규식 예제를](../../standard/base-types/regular-expression-example-scanning-for-hrefs.md)참조하십시오.  
  
- 우편 번호가 유효한 미국 우편 번호여야 하는 경우 우편 번호 웹 서비스를 호출하여 사용자가 입력한 데이터의 유효성을 검사할 수 있습니다.  
  
 이벤트는 <xref:System.Windows.Forms.Control.Validating> 형식의 <xref:System.ComponentModel.CancelEventArgs>개체를 제공 합니다. 컨트롤의 데이터가 유효하지 않다고 판단되면 이 개체의 <xref:System.Windows.Forms.Control.Validating> <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 속성을 로 설정하여 이벤트를 `true`취소할 수 있습니다. <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 속성을 설정하지 않으면 Windows Forms는 해당 컨트롤에 대해 유효성 검사가 <xref:System.Windows.Forms.Control.Validated> 성공했다고 가정하고 이벤트를 발생시면 됩니다.  
  
 에서 전자 메일 주소의 유효성을 <xref:System.Windows.Controls.TextBox>검사하는 <xref:System.Windows.Forms.Control.Validating>코드 예제는 을 참조하십시오.  
  
### <a name="data-binding-and-event-driven-validation"></a>데이터 바인딩 및 이벤트 기반 유효성 검사  
 유효성 검사는 데이터베이스 테이블과 같은 데이터 원본에 컨트롤을 바인딩할 때 매우 유용합니다. 유효성 검사를 사용하면 컨트롤의 데이터가 데이터 원본에 필요한 형식을 정하고 안전하지 않을 수 있는 따옴표 및 백 슬래시와 같은 특수 문자를 포함하지 않도록 할 수 있습니다.  
  
 데이터 바인딩을 사용하면 <xref:System.Windows.Forms.Control.Validating> 컨트롤의 데이터가 이벤트 실행 중에 데이터 원본과 동기화됩니다. <xref:System.Windows.Forms.Control.Validating> 이벤트를 취소하면 데이터가 데이터 원본과 동기화되지 않습니다.  
  
> [!IMPORTANT]
> <xref:System.Windows.Forms.Control.Validating> 이벤트 이후에 수행되는 사용자 지정 유효성 검사가 있는 경우 데이터 바인딩에 영향을 주지 않습니다. 예를 들어 데이터 바인딩을 <xref:System.Windows.Forms.Control.Validated> 취소하려고 시도하는 이벤트에 코드가 있는 경우 데이터 바인딩이 계속 발생합니다. 이 경우 <xref:System.Windows.Forms.Control.Validated> 이벤트에서 유효성 검사를 수행하려면 컨트롤의 **데이터 원본 업데이트 모드** 속성(데이터**바인딩)**\\ **(고급)** 에서 **Onvalidation에서** **절대로**변경하고 유효성 검사 코드에*\<yourFIELD>* `"].WriteValue()` *제어를*`.DataBindings["`추가합니다.  
  
### <a name="implicit-and-explicit-validation"></a>암시적 및 명시적 유효성 검사  
 그렇다면 컨트롤의 데이터는 언제 검증됩니까? 이것은 개발자에게 달려 있습니다. 응용 프로그램의 요구 사항에 따라 암시적 또는 명시적 유효성 검사를 사용할 수 있습니다.  
  
#### <a name="implicit-validation"></a>암시적 유효성 검사  
 암시적 유효성 검사 방법은 사용자가 데이터를 입력할 때 데이터의 유효성을 검사합니다. 키가 누를 때 데이터를 읽거나 사용자가 입력 포커스를 한 컨트롤에서 멀리 가져와 다음 컨트롤로 이동할 때마다 데이터를 컨트롤에 입력할 때 데이터의 유효성을 검사할 수 있습니다. 이 방법은 사용자가 작업하는 데이터에 대한 즉각적인 피드백을 제공하려는 경우에 유용합니다.  
  
 컨트롤에 대한 암시적 유효성 검사를 사용하려면 해당 컨트롤의 <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange> 속성을 <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>또는 로 설정해야 합니다. <xref:System.Windows.Forms.Control.Validating> 이벤트를 취소하면 컨트롤의 동작은 <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>에 할당한 값에 따라 결정됩니다. 할당한 <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>경우 이벤트를 취소하면 <xref:System.Windows.Forms.Control.Validated> 이벤트가 발생하지 않습니다. 입력 포커스는 사용자가 데이터를 올바른 입력으로 변경할 때까지 현재 컨트롤에 유지됩니다. 을 지정하면 <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange> <xref:System.Windows.Forms.Control.Validated> 이벤트를 취소할 때 이벤트가 발생하지 않지만 포커스는 다음 컨트롤로 계속 변경됩니다.  
  
 속성에 <xref:System.Windows.Forms.AutoValidate.Disable> <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> 할당하면 암시적 유효성 검사가 완전히 방지됩니다. 컨트롤의 유효성을 검사하려면 명시적 유효성 검사를 사용해야 합니다.  
  
#### <a name="explicit-validation"></a>명시적 유효성 검사  
 명시적 유효성 검사 방법은 한 번에 데이터의 유효성을 검사합니다. 저장 단추 또는 다음 링크를 클릭하는 등 사용자 작업에 대한 응답으로 데이터의 유효성을 검사할 수 있습니다. 사용자 작업이 발생하면 다음 방법 중 하나로 명시적 유효성 검사를 트리거할 수 있습니다.  
  
- 포커스가 손실된 마지막 컨트롤의 유효성을 검사하기 위해 호출합니다. <xref:System.Windows.Forms.ContainerControl.Validate%2A>  
  
- 폼 <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> 또는 컨테이너 컨트롤의 모든 자식 컨트롤의 유효성을 검사하기 위해 호출합니다.  
  
- 사용자 지정 메서드를 호출하여 컨트롤의 데이터의 유효성을 수동으로 확인합니다.  
  
#### <a name="default-implicit-validation-behavior-for-windows-forms-controls"></a>Windows 양식 컨트롤에 대한 기본 암시적 유효성 검사 동작  
 Windows Forms 컨트롤마다 <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> 해당 속성에 대한 기본값이 다릅니다. 다음 표에서는 가장 일반적인 컨트롤과 해당 기본값을 보여 주었습니다.  
  
|제어|기본 유효성 검사 동작|  
|-------------|---------------------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
|<xref:System.Windows.Forms.PropertyGrid>|비주얼 스튜디오에서 노출되지 않은 속성|  
|<xref:System.Windows.Forms.ToolStripContainer>|비주얼 스튜디오에서 노출되지 않은 속성|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
  
## <a name="closing-the-form-and-overriding-validation"></a>양식 닫기 및 유효성 검사 재정의  
 컨트롤에 포함된 데이터가 유효하지 않으므로 포커스를 유지 관리하는 경우 일반적인 방법 중 하나로 상위 양식을 닫을 수 없습니다.  
  
- **닫기** 버튼을 클릭합니다.  
  
- **시스템** 메뉴에서 **닫기(close)를** 선택합니다.  
  
- 프로그래밍 방식으로 <xref:System.Windows.Forms.Form.Close%2A> 메서드를 호출합니다.  
  
 그러나 경우에 따라 컨트롤의 값이 유효한지 여부에 관계없이 사용자가 폼을 닫도록 할 수 있습니다. 유효성 검사를 재정의하고 양식의 이벤트에 대한 처리기를 만들어 잘못된 데이터가 <xref:System.Windows.Forms.Form.FormClosing> 여전히 포함된 양식을 닫을 수 있습니다. 이 경우 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 속성을 로 `false`설정합니다. 이렇게 하면 폼이 닫힙됩니다. 자세한 내용과 예제는 <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>를 참조하세요.  
  
> [!NOTE]
> 이러한 방식으로 양식을 강제로 닫으면 아직 저장되지 않은 양식 컨트롤의 모든 데이터가 손실됩니다. 또한 모달 양식은 컨트롤이 닫혀 있을 때 컨트롤의 내용을 확인하지 않습니다. 컨트롤 유효성 검사를 사용하여 컨트롤에 포커스를 잠글 수 있지만 폼 닫기와 관련된 동작에 대해 걱정할 필요는 없습니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.Control.Validating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>
- <xref:System.Windows.Forms.FormClosingEventArgs?displayProperty=nameWithType>
- [MaskedTextBox 컨트롤](./controls/maskedtextbox-control-windows-forms.md)
- [정규 표현식 예제](../../standard/base-types/regular-expression-example-scanning-for-hrefs.md)
