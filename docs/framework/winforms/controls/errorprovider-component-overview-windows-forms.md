---
title: ErrorProvider 구성 요소 개요
ms.date: 03/30/2017
f1_keywords:
- ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
ms.openlocfilehash: b66e97d97d0d8c2ea4e9bdba29f8ff35e486e1f6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745798"
---
# <a name="errorprovider-component-overview-windows-forms"></a>ErrorProvider 구성 요소 개요(Windows Forms)
Windows Forms [ErrorProvider](errorprovider-component-windows-forms.md) 구성 요소는 폼 이나 컨트롤에서 사용자 입력의 유효성을 검사 하는 데 사용 됩니다. 일반적으로 폼에서 사용자 입력의 유효성을 검사 하거나 데이터 집합 내에 오류를 표시 하는 것과 함께 사용 됩니다. 메시지 상자를 해제 하면 오류 메시지가 더 이상 표시 되지 않기 때문에 오류 공급자는 메시지 상자에 오류 메시지를 표시 하는 것 보다 더 나은 방법입니다. <xref:System.Windows.Forms.ErrorProvider> 구성 요소는 텍스트 상자와 같은 관련 컨트롤 옆에 있는 오류 아이콘 (빨간색 원 안에 흰색 느낌표를![.](./media/errorprovider-component-overview-windows-forms/vb-error-provider-icon.gif))을 표시 합니다. 사용자가 마우스 포인터를 오류 아이콘 위로 가져가면 오류 메시지 문자열을 보여 주는 도구 설명이 나타납니다.  
  
## <a name="key-properties"></a>키 속성  
 <xref:System.Windows.Forms.ErrorProvider> 구성 요소의 키 속성은 <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>및 <xref:System.Windows.Forms.ErrorProvider.Icon%2A>입니다. 데이터 바인딩된 컨트롤에서 <xref:System.Windows.Forms.ErrorProvider> 구성 요소를 사용 하는 경우 구성 요소가 폼에 오류 아이콘을 표시 하려면 <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> 속성을 적절 한 컨테이너 (일반적으로 Windows Form)로 설정 해야 합니다. 디자이너에서 구성 요소를 추가 하면 <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> 속성이 포함 폼으로 설정 됩니다. 코드에 컨트롤을 추가 하는 경우 직접 설정 해야 합니다.  
  
 <xref:System.Windows.Forms.ErrorProvider.Icon%2A> 속성은 기본값이 아닌 사용자 지정 오류 아이콘으로 설정할 수 있습니다. <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> 속성이 설정 되 면 <xref:System.Windows.Forms.ErrorProvider> 구성 요소가 데이터 집합에 대 한 오류 메시지를 표시할 수 있습니다. <xref:System.Windows.Forms.ErrorProvider> 구성 요소의 주요 메서드는 오류 메시지 문자열을 지정 하 고 오류 아이콘이 표시 되어야 하는 <xref:System.Windows.Forms.ErrorProvider.SetError%2A> 메서드입니다.  
  
> [!NOTE]
> <xref:System.Windows.Forms.ErrorProvider> 구성 요소 액세스 가능 클라이언트에 대 한 기본 제공 지원을 제공 하지 않습니다. 이 구성 요소를 사용 하는 경우 애플리케이션에 액세스할 수 있도록, 추가, 액세스할 수 있는 피드백 메커니즘을 제공 해야 합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.ErrorProvider>
- [방법: Windows Forms ErrorProvider 구성 요소를 사용하여 데이터 세트에 있는 오류 보기](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
- [방법: Windows Forms ErrorProvider 구성 요소를 사용하여 폼 유효성에 대한 오류 아이콘 표시](display-error-icons-for-form-validation-with-wf-errorprovider.md)
