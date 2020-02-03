---
title: 간단한 컨트롤 개발
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms]
- custom controls [Windows Forms], creating simple controls using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 86cbe435-45b7-4cb4-9b5a-47418369758d
ms.openlocfilehash: 5383cee5358dbd260fc6c023d3db607da6b10ea4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742262"
---
# <a name="how-to-develop-a-simple-windows-forms-control"></a>방법: 간단한 Windows Forms 컨트롤 개발

이 섹션에서는 사용자 지정 Windows Forms 컨트롤을 작성하는 주요 단계를 설명합니다. 이 연습에서 개발한 간단한 컨트롤을 사용 하면 <xref:System.Windows.Forms.Control.Text%2A> 속성을 변경할 수 있습니다. 이벤트를 발생시키거나 처리하지 않습니다.

### <a name="to-create-a-simple-custom-control"></a>간단한 사용자 지정 컨트롤을 만들려면

1. <xref:System.Windows.Forms.Control?displayProperty=nameWithType>에서 파생된 클래스를 정의합니다.

    ```vb
    Public Class FirstControl
       Inherits Control

    End Class
    ```

    ```csharp
    public class FirstControl:Control {}
    ```

2. 속성을 정의합니다. 컨트롤은 <xref:System.Windows.Forms.Control> 클래스에서 많은 속성을 상속 하지만 대부분의 사용자 지정 컨트롤은 일반적으로 추가 속성을 정의 하므로 속성을 정의할 필요가 없습니다. 다음 코드 조각은 <xref:System.Windows.Forms.Control>에서 상속 된 <xref:System.Windows.Forms.Control.Text%2A> 속성의 표시 형식을 지정 하는 데 사용할 `FirstControl` `TextAlignment` 라는 속성을 정의 합니다. 속성을 정의하는 방법에 대한 자세한 내용은 [속성 개요](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v%3dvs.120))를 참조하세요.

     [!code-csharp[System.Windows.Forms.FirstControl#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#3)]
     [!code-vb[System.Windows.Forms.FirstControl#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#3)]

     컨트롤의 시각적 표시를 변경 하는 속성을 설정 하는 경우 <xref:System.Windows.Forms.Control.Invalidate%2A> 메서드를 호출 하 여 컨트롤을 다시 그려야 합니다. <xref:System.Windows.Forms.Control.Invalidate%2A>은 기본 클래스 <xref:System.Windows.Forms.Control>에 정의 되어 있습니다.

3. <xref:System.Windows.Forms.Control>에서 상속 된 protected <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의 하 여 컨트롤에 렌더링 논리를 제공 합니다. <xref:System.Windows.Forms.Control.OnPaint%2A>를 재정의 하지 않으면 컨트롤은 자체적으로 그릴 수 없습니다. 다음 코드 조각에서 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드는 `alignmentValue` 필드로 지정 된 맞춤을 사용 하 여 <xref:System.Windows.Forms.Control>에서 상속 된 <xref:System.Windows.Forms.Control.Text%2A> 속성을 표시 합니다.

     [!code-csharp[System.Windows.Forms.FirstControl#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#4)]
     [!code-vb[System.Windows.Forms.FirstControl#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#4)]

4. 컨트롤의 특성을 제공합니다. 특성을 사용하면 시각적 디자이너가 디자인 타임에 컨트롤과 해당 속성 및 이벤트를 적절하게 표시할 수 있습니다. 다음 코드 조각은 `TextAlignment` 속성에 특성을 적용합니다. Visual Studio와 같은 디자이너에서 <xref:System.ComponentModel.CategoryAttribute.Category%2A> 특성 (코드 조각에 표시)을 수행 하면 속성이 논리적 범주 아래에 표시 됩니다. <xref:System.ComponentModel.DescriptionAttribute.Description%2A> 특성은 `TextAlignment` 속성이 선택 된 경우 **속성** 창 맨 아래에 설명 문자열이 표시 되도록 합니다. 특성에 대한 자세한 내용은 [구성 요소에 대한 디자인 타임 특성](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))을 참조하세요.

     [!code-csharp[System.Windows.Forms.FirstControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#5)]
     [!code-vb[System.Windows.Forms.FirstControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#5)]

5. (선택 사항)컨트롤에 리소스를 제공합니다. 컨트롤과 함께 리소스를 패키징하는 컴파일러 옵션(C#의 경우 `/res`)을 사용하여 컨트롤에 비트맵과 같은 리소스를 제공할 수 있습니다. 런타임에 <xref:System.Resources.ResourceManager> 클래스의 메서드를 사용 하 여 리소스를 검색할 수 있습니다. 리소스를 만들고 사용하는 방법에 대한 자세한 내용은 [데스크톱 앱의 리소스](../../resources/index.md)를 참조하세요.

6. 컨트롤을 컴파일하고 배포합니다. `FirstControl,`을 컴파일하고 배포하려면 다음 단계를 실행합니다.

    1. 다음 샘플의 코드를 소스 파일(예: FirstControl.cs 또는 FirstControl.vb)에 저장합니다.

    2. 소스 코드를 어셈블리로 컴파일하고 애플리케이션의 디렉터리에 저장합니다. 이를 수행하려면 소스 파일이 포함된 디렉터리에서 다음 명령을 실행합니다.

        ```console
        vbc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.vb
        ```

        ```console
        csc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.cs
        ```

         `/t:library` 컴파일러 옵션은 사용자가 만드는 어셈블리가 실행 파일이 아니라 라이브러리임을 컴파일러에 알립니다. `/out` 옵션은 어셈블리의 경로 및 이름을 지정합니다. `/r` 옵션은 코드에 의해 참조되는 어셈블리의 이름을 제공합니다. 이 예제에서는 애플리케이션에서만 사용할 수 있는 프라이빗 어셈블리를 만들 수 있습니다. 따라서 애플리케이션의 디렉터리에 저장해야 합니다. 배포하기 위한 컨트롤을 패키징하고 배포하는 방법에 대한 자세한 내용은 [배포](../../deployment/index.md)를 참조하세요.

다음 샘플은 `FirstControl`의 코드를 보여 줍니다. 컨트롤은 네임스페이스 `CustomWinControls`에서 따옴표로 묶입니다. 네임스페이스는 관련된 형식의 논리적 그룹화를 제공합니다. 새로운 또는 기존 네임스페이스에서 컨트롤을 만들 수 있습니다. C#에서 `using` 선언(Visual Basic의 경우 `Imports`)을 사용하면 형식의 정규화된 이름을 사용하지 않고 네임스페이스에서 형식에 액세스할 수 있습니다. 다음 예제에서는 `using` 선언을 사용 하 여 코드에서 <xref:System.Windows.Forms.Control> 정규화 된 이름 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>를 사용 하는 대신 <xref:System.Windows.Forms.Control> <xref:System.Windows.Forms?displayProperty=nameWithType>에서 클래스에 액세스할 수 있습니다.

[!code-csharp[System.Windows.Forms.FirstControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#1)]
[!code-vb[System.Windows.Forms.FirstControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#1)]

## <a name="using-the-custom-control-on-a-form"></a>양식에서 사용자 지정 컨트롤 사용

다음 예제에서는 `FirstControl`을 사용하는 간단한 양식을 보여 줍니다. `FirstControl` 속성에 대해 각각 다른 값을 가진 세 개의 `TextAlignment` 인스턴스를 만듭니다.

#### <a name="to-compile-and-run-this-sample"></a>이 샘플을 컴파일하고 실행하려면

1. 소스 파일(SimpleForm.cs 또는 SimpleForms.vb)에 다음 예제의 코드를 저장합니다.

2. 소스 파일을 포함하는 디렉터리에서 다음 명령을 실행하여 소스 코드를 실행 가능한 어셈블리로 컴파일합니다.

    ```console
    vbc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.vb
    ```

    ```console
    csc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.cs
    ```

     CustomWinControls .dll은 `FirstControl`클래스가 포함 된 어셈블리입니다. 이 어셈블리는 액세스하는 양식의 소스 파일과 동일한 디렉터리에 있어야 합니다(SimpleForm.cs 또는 SimpleForms.vb).

3. 다음 명령을 사용하여 SimpleForm.exe를 실행합니다.

    ```console
    SimpleForm
    ```

[!code-csharp[System.Windows.Forms.FirstControl#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/SimpleForm.cs#10)]
[!code-vb[System.Windows.Forms.FirstControl#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/SimpleForm.vb#10)]

## <a name="see-also"></a>참고 항목

- [Windows Forms 컨트롤의 속성](properties-in-windows-forms-controls.md)
- [Windows Forms 컨트롤의 이벤트](events-in-windows-forms-controls.md)
