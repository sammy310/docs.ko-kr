---
title: ErrorProvider 구성 요소 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
ms.openlocfilehash: 485e7a17073d72618b9599113179cddde748e697
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181183"
---
# <a name="errorprovider-component-overview-windows-forms"></a>ErrorProvider 구성 요소 개요(Windows Forms)
Windows Forms [ErrorProvider](errorprovider-component-windows-forms.md) 폼 이나 컨트롤에서 사용자 입력 유효성 검사 구성 요소를 사용 합니다. 일반적으로 폼에서 사용자 입력 유효성 검사 또는 데이터 집합 내에서 오류 표시와 함께에서 사용 됩니다. 오류 공급자 메시지 상자에 오류 메시지를 표시 하는 보다 더 나은 방법은 이므로 메시지 상자 해제 되 면 오류 메시지를 더 표시 되지 않습니다. <xref:System.Windows.Forms.ErrorProvider> 오류 아이콘을 표시 하는 구성 요소 (![ErrorProvider 아이콘](./media/vberrorprovidericon.gif "vbErrorProviderIcon")) 텍스트 상자; 위에 마우스 포인터를 놓을 때와 같은 관련 컨트롤 옆에 도구 설명이 나타납니다 오류 아이콘, 오류 메시지 문자열을 표시 합니다.  
  
## <a name="key-properties"></a>키 속성  
 합니다 <xref:System.Windows.Forms.ErrorProvider> 구성 요소의 주요 속성은 <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>를 <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>, 및 <xref:System.Windows.Forms.ErrorProvider.Icon%2A>합니다. 사용 하는 경우 <xref:System.Windows.Forms.ErrorProvider> 데이터 바인딩된 컨트롤을 사용 하 여 구성 요소는 <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> 양식의 오류 아이콘을 표시 하려면 구성 요소에서 속성을 적절 한 컨테이너 (일반적으로 Windows 폼)을 설정 해야 합니다. 구성 요소 디자이너에 추가 되 면는 <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> 포함 하는 폼 속성이; 코드에서 컨트롤을 추가 하는 경우 있습니다 직접 설정 해야 합니다.  
  
 <xref:System.Windows.Forms.ErrorProvider.Icon%2A> 기본값 대신 사용자 지정 오류 아이콘으로 속성을 설정할 수 있습니다. 경우는 <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> 속성을 설정 합니다 <xref:System.Windows.Forms.ErrorProvider> 구성 요소는 데이터 집합에 대 한 오류 메시지를 표시할 수 있습니다. 주요 메서드는 <xref:System.Windows.Forms.ErrorProvider> 구성 요소는는 <xref:System.Windows.Forms.ErrorProvider.SetError%2A> 에 오류 아이콘이 표시 되 고 오류 메시지 문자열을 지정 하는 메서드.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ErrorProvider> 구성 요소 액세스 가능 클라이언트에 대 한 기본 제공 지원을 제공 하지 않습니다. 이 구성 요소를 사용 하는 경우 응용 프로그램에 액세스할 수 있도록, 추가, 액세스할 수 있는 피드백 메커니즘을 제공 해야 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.ErrorProvider>
- [방법: Windows Forms ErrorProvider 구성 요소를 사용하여 DataSet 내의 오류 보기](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
- [방법: Windows Forms ErrorProvider 구성 요소를 사용하여 양식 유효성 오류 아이콘 표시](display-error-icons-for-form-validation-with-wf-errorprovider.md)
