---
title: '호환성이 손상되는 변경: 네이티브 코드에서 WinForms 개체에 액세스할 수 없음'
description: 더 이상 네이티브 코드에서 Windows Forms 개체에 액세스할 수 없는 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 01/29/2021
ms.openlocfilehash: 53343f3f07817f735fa3b0ee77a352dcc80d4b6c
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506493"
---
# <a name="native-code-cant-access-windows-forms-objects"></a>네이티브 코드는 Windows Forms 개체에 액세스하지 못함

.NET 5.0부터 더 이상 네이티브 코드에서 Windows Forms 개체에 액세스할 수 없습니다.

## <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서는 일부 Windows Forms 형식이 COM interop에 표시되는 것으로 데코레이팅되었으므로 네이티브 코드에서 액세스할 수 있었습니다. .NET 5.0부터 Windows Forms API는 COM interop에 표시되거나 네이티브 코드에 액세스할 수 없습니다. .NET 런타임은 더 이상 기본적으로 사용자 지정 형식 라이브러리 만들기를 지원하지 않습니다. 또한 .NET 런타임은 .NET Framework에 대한 형식 라이브러리에 의존할 수 없습니다(.NET Framework에 있는 것처럼 클래스의 모양을 유지해야 함).

## <a name="reason-for-change"></a>변경 이유

- 형식 라이브러리(TLB 파일) 생성 및 조회에 사용된 열거에서 `ComVisible(true)` 제거: .NET Core에서 제공하는 WinForms TLB가 없으므로 이 특성을 유지하는 값이 없습니다.
- `AccessibleObject` 클래스에서 `ComVisible(true)` 제거: 이러한 클래스는 CoCreateable(매개 변수가 없는 생성자가 없음)이 아니며, 이미 존재하는 인스턴스를 COM에 노출하는 경우 해당 특성이 필요하지 않습니다.
- `Control` 및 `Component` 클래스에서 `ComVisible(true)` 제거: 이 특성은 예를 들어 VB6 또는 MFC에서 OLE/ActiveX를 통해 WinForms 컨트롤을 호스트하는 데 사용되었습니다. 그러나 이를 위해서는 더 이상 제공되지 않는 WinForms에 대한 TLB가 필요하고 기본적으로는 작동하지 않는 레지스트리 기반 활성화도 필요합니다. 일반적으로 WinForms 컨트롤의 COM 기반 호스팅은 유지 관리되지 않았으므로 이를 미지원 상태로 유지하는 대신 지원을 중단했습니다.
- 컨트롤에서 `ClassInterface` 특성 제거: OLE/ActiveX를 통한 호스팅을 지원하지 않는 경우 이러한 특성은 더 이상 필요하지 않습니다. 이들은 개체가 여전히 COM에 노출되고 특성이 관련될 수 있는 다른 위치에서는 유지됩니다.
- `EventArgs`에서 `ComVisible(true)` 제거: 이들은 주로 더 이상 지원되지 않는 OLE/ActiveX 호스팅에서 사용될 가능성이 높았습니다. CoCreateable도 아니므로 이 특성은 목적이 없습니다. 또한 TLB를 제공하지 않고 기존 인스턴스를 노출하는 것은 의미가 없습니다.
- 대리자에서 `ComVisible(true)` 제거: 용도를 알 수 없지만 WinForms 컨트롤의 ActiveX 호스팅이 더 이상 지원되지 않으므로 유용성이 없을 가능성이 높습니다.
- 일부 공용이 아닌 코드에서 `ComVisible(true)` 제거: 잠재적 소비자는 새로운 Visual Studio 디자이너가 유일하지만 GUID를 지정하지 않으면 계속 필요할 가능성이 거의 없습니다.
- 일부 임의 공용 디자이너 클래스에서 `ComVisible(true)` 제거: 이전 Visual Studio 디자이너가 COM interop을 사용하여 이러한 클래스와 통신해 왔을 수 있습니다. 그러나 이전 디자이너는 .NET Core를 지원하지 않으므로 이들 클래스가 `ComVisible`이어야 하는 경우는 거의 없습니다.
- `IWin32Window`는 .NET Framework에 정의된 것과 동일한 GUID를 정의했으며, 이는 위험한 결과를 초래합니다. .NET Framework 상호 운용성이 필요한 경우 `ComImport`를 사용합니다.
- WinForms 관리되는 `IDataObject`가 `ComVisible`이 되었습니다. 이는 필요하지 않으며 `IDataObject` COM interop에 대한 별도의 `ComImport` 인터페이스 선언이 있습니다. TLB가 제공되지 않고 마샬링이 항상 실패하기 때문에 관리되는 `IDataObject`가 `ComVisible`이면 오히려 역효과가 일어납니다. 또한 GUID가 지정되지 않았고 .NET Framework와 달랐기 때문에 문서화되지 않은 IID를 제거해도 고객에게 부정적인 영향을 미칠 가능성이 없습니다.
- `ComVisible(false)` 제거: 이들은 표면상 임의의 위치에 배치되며 클래스를 COM interop에 노출하는 것이 기본값이 아닌 경우 중복입니다.

## <a name="version-introduced"></a>도입된 버전

.NET 5.0

## <a name="recommended-action"></a>권장 조치

다음 예제는 .NET Framework 및 .NET Core 3.1에서 작동합니다. 이 예제는 JavaScript가 리플렉션을 통해 양식 하위 클래스로 콜백할 수 있도록 하는 .NET Framework 형식 라이브러리에 의존합니다.

```cs
[PermissionSet(SecurityAction.Demand, Name="FullTrust")]
[System.Runtime.InteropServices.ComVisibleAttribute(true)]
public class Form1 : Form
{
    private WebBrowser webBrowser1 = new WebBrowser();

    protected override void OnLoad(EventArgs e)
    {
        webBrowser1.AllowWebBrowserDrop = false;
        webBrowser1.IsWebBrowserContextMenuEnabled = false;
        webBrowser1.WebBrowserShortcutsEnabled = false;
        webBrowser1.ObjectForScripting = this;

        webBrowser1.DocumentText =
            "<html><body><button " +
            "onclick=\"window.external.Test('called from script code')\">" +
            "call client code from script code</button>" +
            "</body></html>";
    }

    public void Test(String message)
    {
        MessageBox.Show(message, "client code");
    }
}
```

이 예제가 .NET 5.0 이상 버전에서 작동하도록 할 수 있는 방법은 두 가지가 있습니다.

- 프로젝트 수준에서 명시적으로 변경되지 않는 한 기본적으로 적용되는 `IDispatch`를 지원하는 사용자 선언 `ObjectForScripting` 개체를 도입합니다.

  ```cs
  public class MyScriptObject
  {
      private Form1 _form;

      public MyScriptObject(Form1 form)
      {
          _form = form;
      }

      public void Test(string message)
      {
          MessageBox.Show(message, "client code");
      }
  }

  public partial class Form1 : Form
  {
      protected override void OnLoad(EventArgs e)
      {
          ...

          // Works correctly.
          webBrowser1.ObjectForScripting = new MyScriptObject(this);

          ...
      }
  }
  ```

- 노출할 메서드와의 인터페이스를 선언합니다.

  ```cs
  public interface IForm1
  {
      void Test(string message);
  }

  [ComDefaultInterface(typeof(IForm1))]
  public partial class Form1 : Form, IForm1
  {
      protected override void OnLoad(EventArgs e)
      {
          ...

          // Works correctly.
          webBrowser1.ObjectForScripting = this;

          ...
      }
  }
  ```

## <a name="affected-apis"></a>영향을 받는 API

모든 Windows Forms API.

<!--

### Category

- Windows Forms

-->
