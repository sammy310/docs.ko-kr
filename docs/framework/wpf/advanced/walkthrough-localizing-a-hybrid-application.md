---
title: '연습: 혼합 애플리케이션 지역화'
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 69aa5ae145ffe378b7a4547e5a33826965bf7894
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111116"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a>연습: 혼합 애플리케이션 지역화

이 연습에서는 Windows Forms [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기반 하이브리드 응용 프로그램의 요소를 지역화하는 방법을 보여 주어집니다.

이 연습에서 설명하는 작업은 다음과 같습니다.

- Windows Forms 호스트 프로젝트 만들기

- 지역화 가능한 콘텐츠 추가.

- 지역화 사용.

- 리소스 식별자 할당.

- LocBaml 도구를 사용하여 위성 어셈블리 생성.

이 연습에 설명된 작업의 전체 코드 목록은 [하이브리드 응용 프로그램 샘플 지역 화를](https://go.microsoft.com/fwlink/?LinkID=160015)참조하십시오.

위의 작업을 완료하면 지역화된 하이브리드 애플리케이션이 구현됩니다.

## <a name="prerequisites"></a>전제 조건

이 연습을 완료하려면 다음과 같은 구성 요소가 필요합니다.

- Visual Studio 2017

## <a name="creating-the-windows-forms-host-project"></a>Windows Forms 호스트 프로젝트 만들기

첫 번째 단계는 Windows Forms 응용 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로젝트를 만들고 지역화할 콘텐츠가 있는 요소를 추가하는 것입니다.

### <a name="to-create-the-host-project"></a>호스트 프로젝트 만들기

1. 라는 **WPF 앱** `LocalizingWpfInWf`프로젝트를 만듭니다.  (파일**File** > **새** > **프로젝트** > 비주얼 C **#** 또는 **비주얼 기본** > 클래식**데스크톱** > **WPF 응용 프로그램).**

2. 프로젝트에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 호출된 `SimpleControl` 요소를 추가합니다.

3. 컨트롤을 <xref:System.Windows.Forms.Integration.ElementHost> 사용하여 `SimpleControl` 폼에 요소를 배치합니다. 자세한 내용은 [연습: Windows 양식에서 3D WPF 복합 제어 호스팅을](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)참조하십시오.

## <a name="adding-localizable-content"></a>지역화 가능한 콘텐츠 추가

그런 다음 Windows Forms 레이블 컨트롤을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 추가하고 요소의 내용을 지역화 가능한 문자열로 설정합니다.

### <a name="to-add-localizable-content"></a>지역화 가능한 콘텐츠를 추가하려면

1. **솔루션 탐색기에서** **SimpleControl.xaml을** 두 번 클릭하여 WPF 디자이너에서 엽니다.

2. 다음 코드를 사용하여 <xref:System.Windows.Controls.Button> 컨트롤의 내용을 설정합니다.

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. **솔루션 탐색기에서** **Form1을** 두 번 클릭하여 Windows 양식 디자이너에서 엽니다.

4. 도구 **상자를** 열고 **레이블을** 두 번 클릭하여 양식에 레이블 컨트롤을 추가합니다. <xref:System.Windows.Forms.Control.Text%2A> 속성의 값을 `"Hello"`로 설정합니다.

5. **F5를** 눌러 응용 프로그램을 빌드하고 실행합니다.

     `SimpleControl` 요소와 레이블 컨트롤 모두 **"Hello"** 텍스트를 표시합니다.

## <a name="enabling-localization"></a>지역화 사용

Windows Forms 디자이너에서는 위성 어셈블리에서 지역화를 사용하도록 설정하기 위한 설정을 제공합니다.

### <a name="to-enable-localization"></a>지역화를 사용하려면

1. **솔루션 탐색기에서** **Form1.cs** 두 번 클릭하여 Windows 양식 디자이너에서 엽니다.

2. **속성** 창에서 양식의 **지역화 가능한** 속성의 값을 `true`으로 설정합니다.

3. **속성** 창에서 **Language** 속성의 값을 **스페인어(스페인)로**설정합니다.

4. Windows Forms 디자이너에서 레이블 컨트롤을 선택합니다.

5. **속성** 창에서 <xref:System.Windows.Forms.Control.Text%2A> 속성 값을 `"Hola"`으로 설정합니다.

     Form1.es-ES.resx라는 새 리소스 파일이 프로젝트에 추가됩니다.

6. **솔루션 탐색기에서** **Form1.cs** 마우스 오른쪽 단추로 클릭하고 **코드 보기를** 클릭하여 코드 편집기에서 엽니다.

7. 다음 코드를 `Form1` 호출하기 전에 생성자로 복사합니다. `InitializeComponent`

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. **솔루션 탐색기에서** **지역화WpfInWf를** 마우스 오른쪽 버튼으로 클릭하고 **프로젝트 언로드를**클릭합니다.

     프로젝트 이름은 **레이블이 지정됩니다(사용할 수 없음).**

9. 오른쪽 에서 **지역화WpfInWf를**클릭하고 **지역화 WpfInWf.csproj 편집을**클릭합니다.

     프로젝트 파일이 코드 편집기에서 열립니다.

10. 다음 줄을 프로젝트 파일의 첫 번째 `PropertyGroup` 줄에 복사합니다.

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. 프로젝트 파일을 저장하고 닫습니다.

12. **솔루션 탐색기에서** **지역화WpfInWf를** 마우스 오른쪽 버튼으로 클릭하고 **프로젝트 다시로드를**클릭합니다.

## <a name="assigning-resource-identifiers"></a>리소스 식별자 할당

리소스 식별자를 사용하여 리소스 어셈블리에 지역화 가능한 콘텐츠를 매핑할 수 있습니다. MsBuild.exe 응용 프로그램은 옵션을 지정할 때 리소스 `updateuid` 식별자를 자동으로 할당합니다.

### <a name="to-assign-resource-identifiers"></a>리소스 식별자를 할당하려면

1. 시작 메뉴에서 Visual Studio에 대한 개발자 명령 프롬프트를 엽니다.

2. 다음 명령을 사용하여 지역화 가능한 콘텐츠에 리소스 식별자를 할당합니다.

    ```console
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. **솔루션 탐색기에서** **SimpleControl.xaml을** 두 번 클릭하여 코드 편집기에서 엽니다. 명령이 `msbuild` 모든 요소에 `Uid` 속성을 추가한 것을 볼 수 있습니다. 따라서 리소스 식별자 할당을 통해 지역화가 용이해집니다.

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. **F6** 키를 눌러 솔루션을 빌드합니다.

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a>LocBaml을 사용하여 위성 어셈블리 생성

지역화된 콘텐츠는 리소스 전용 *위성 어셈블리에*저장됩니다. 명령줄 도구 LocBaml.exe를 사용하여 콘텐츠에 대한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 지역화된 어셈블리를 생성합니다.

### <a name="to-produce-a-satellite-assembly"></a>위성 어셈블리를 생성하려면

1. LocBaml.exe를 프로젝트의 obj\Debug 폴더에 복사합니다. 자세한 내용은 [응용 프로그램 지역화](how-to-localize-an-application.md)를 참조하십시오.

2. [명령 프롬프트] 창에서 다음 명령을 사용하여 리소스 문자열을 임시 파일로 추출합니다.

    ```console
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. Visual Studio 또는 다른 텍스트 편집기에서 temp.csv 파일을 엽니다. 문자열을 `"Hello"` 스페인어 번역으로 `"Hola"`바꿉습니다.

4. temp.csv 파일을 저장합니다.

5. 다음 명령을 사용하여 지역화된 리소스 파일을 생성합니다.

    ```console
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     LocalizingWpfInWf.g.es-ES.resources 파일이 obj\Debug 폴더에 만들어집니다.

6. 다음 명령을 사용하여 지역화된 위성 어셈블리를 빌드합니다.

    ```console
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     LocalizingWpfInWf.resources.dll 파일이 obj\Debug 폴더에 만들어집니다.

7. LocalizingWpfInWf.resources.dll 파일을 프로젝트의 bin\Debug\es-ES 폴더에 복사합니다. 기존 파일을 바꿉니다.

8. 프로젝트의 bin\Debug 폴더에 있는 LocalizingWpfInWf.exe를 실행합니다. 애플리케이션을 다시 빌드하지 마세요. 다시 빌드하면 위성 어셈블리가 덮어 쓰입니다.

     애플리케이션에서 영어 문자열 대신 지역화된 문자열을 표시합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [애플리케이션 지역화](how-to-localize-an-application.md)
- [연습: Windows Forms 지역화](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))
- [Visual Studio에서 XAML 디자인](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
