---
title: Windows Forms에 대 한 WPF 컨트롤 선택
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 19f1dfec282b025f5a1fa367ec5fa9a52472c691
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746805"
---
# <a name="walkthrough-assign-wpf-content-on-windows-forms-at-design-time"></a>연습: 디자인 타임에 Windows Forms에 WPF 콘텐츠 할당

이 문서에서는 폼에 표시 하려는 Windows Presentation Foundation (WPF) 컨트롤 형식을 선택 하는 방법을 보여 줍니다. 프로젝트에 포함 된 모든 WPF 컨트롤 형식을 선택할 수 있습니다.

## <a name="prerequisites"></a>전제 조건

이 연습을 완료하려면 Visual Studio가 필요합니다.

## <a name="create-the-project"></a>프로젝트를 만듭니다.

Visual Studio를 열고 Visual Basic 또는 `SelectingWpfContent`라는 시각적 개체 C# 에서 새 Windows Forms 응용 프로그램 프로젝트를 만듭니다.

> [!NOTE]
> WPF 콘텐츠를 호스트하는 경우 C# 및 Visual Basic 프로젝트만 지원됩니다.

## <a name="create-the-wpf-control-types"></a>WPF 컨트롤 형식 만들기

프로젝트에 WPF 컨트롤 형식을 추가한 후 다양한 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트할 수 있습니다.

1. 새 WPF <xref:System.Windows.Controls.UserControl> 프로젝트를 솔루션에 추가합니다. 컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다. 자세한 내용은 [연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)를 참조 하세요.

2. 디자인 뷰에서 `UserControl1`이 선택되었는지 확인합니다.

3. **속성** 창에서 <xref:System.Windows.FrameworkElement.Width%2A> 값을 설정 하 고 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 **200**으로 설정 합니다.

4. <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤을 <xref:System.Windows.Controls.UserControl>에 추가 하 고 <xref:System.Windows.Controls.TextBox.Text%2A> 속성의 값을 **Hosted Content**로 설정 합니다.

5. 프로젝트에 두 번째 WPF <xref:System.Windows.Controls.UserControl>을 추가합니다. 컨트롤 형식의 기본 이름인 `UserControl2.xaml`을 사용합니다.

6. **속성** 창에서 <xref:System.Windows.FrameworkElement.Width%2A> 값을 설정 하 고 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 **200**으로 설정 합니다.

7. <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤을 <xref:System.Windows.Controls.UserControl>에 추가 하 고 <xref:System.Windows.Controls.TextBox.Text%2A> 속성의 값을 **호스트 된 콘텐츠 2**로 설정 합니다.

   > [!NOTE]
   > 일반적으로 더 복잡한 WPF 콘텐츠를 호스트해야 합니다. <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤은 여기서 설명 목적으로만 사용됩니다.

8. 프로젝트를 빌드합니다.

## <a name="select-wpf-controls"></a>WPF 컨트롤 선택

이미 콘텐츠를 호스트하고 있는 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에 다른 WPF 콘텐츠를 할당할 수 있습니다.

1. Windows Forms 디자이너에서 `Form1`을 엽니다.

2. **도구 상자**에서 `UserControl1`를 두 번 클릭 하 여 폼에 `UserControl1`의 인스턴스를 만듭니다.

   `UserControl1` 인스턴스가 `elementHost1`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.

3. `elementHost1`에 대 한 스마트 태그 패널에서 **호스팅된 콘텐츠 선택** 드롭다운 목록을 엽니다.

4. 드롭다운 목록 상자에서 **UserControl2** 를 선택 합니다.

   이제 `elementHost1` 컨트롤이 `UserControl2` 형식의 인스턴스를 호스트합니다.

5. **속성** 창에서 <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> 속성이 **UserControl2**으로 설정 되어 있는지 확인 합니다.

6. **도구 상자**의 **WPF 상호 운용성** 그룹에서 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 폼으로 끌어옵니다.

   새 컨트롤의 기본 이름은 `elementHost2`입니다.

7. `elementHost2`에 대 한 스마트 태그 패널에서 **호스팅된 콘텐츠 선택** 드롭다운 목록을 엽니다.

8. 드롭다운 목록에서 **UserControl1** 을 선택 합니다.

9. 이제 `elementHost2` 컨트롤이 `UserControl1` 형식의 인스턴스를 호스트합니다.

## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [마이그레이션 및 상호 운용성](../../wpf/advanced/migration-and-interoperability.md)
- [WPF 컨트롤 사용](using-wpf-controls.md)
- [Visual Studio에서 XAML 디자인](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
