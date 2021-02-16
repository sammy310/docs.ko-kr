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
# <a name="native-code-cant-access-windows-forms-objects"></a><span data-ttu-id="cb641-103">네이티브 코드는 Windows Forms 개체에 액세스하지 못함</span><span class="sxs-lookup"><span data-stu-id="cb641-103">Native code can't access Windows Forms objects</span></span>

<span data-ttu-id="cb641-104">.NET 5.0부터 더 이상 네이티브 코드에서 Windows Forms 개체에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-104">Starting in .NET 5.0, you can no longer access Windows Forms objects from native code.</span></span>

## <a name="change-description"></a><span data-ttu-id="cb641-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="cb641-105">Change description</span></span>

<span data-ttu-id="cb641-106">이전 .NET 버전에서는 일부 Windows Forms 형식이 COM interop에 표시되는 것으로 데코레이팅되었으므로 네이티브 코드에서 액세스할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-106">In previous .NET versions, some Windows Forms types were decorated as visible to COM interop, and thus were accessible to native code.</span></span> <span data-ttu-id="cb641-107">.NET 5.0부터 Windows Forms API는 COM interop에 표시되거나 네이티브 코드에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-107">Starting in .NET 5.0, no Windows Forms API are visible to COM interop or accessible to native code.</span></span> <span data-ttu-id="cb641-108">.NET 런타임은 더 이상 기본적으로 사용자 지정 형식 라이브러리 만들기를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-108">The .NET runtime no longer supports creating custom type libraries out of the box.</span></span> <span data-ttu-id="cb641-109">또한 .NET 런타임은 .NET Framework에 대한 형식 라이브러리에 의존할 수 없습니다(.NET Framework에 있는 것처럼 클래스의 모양을 유지해야 함).</span><span class="sxs-lookup"><span data-stu-id="cb641-109">In addition, the .NET runtime can't depend on the type library for .NET Framework (which would require maintaining the shape of classes as they were in .NET Framework).</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="cb641-110">변경 이유</span><span class="sxs-lookup"><span data-stu-id="cb641-110">Reason for change</span></span>

- <span data-ttu-id="cb641-111">형식 라이브러리(TLB 파일) 생성 및 조회에 사용된 열거에서 `ComVisible(true)` 제거: .NET Core에서 제공하는 WinForms TLB가 없으므로 이 특성을 유지하는 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-111">Removal of `ComVisible(true)` from enumerations that were used for type library (TLB file) generation and lookup: Since there is no WinForms TLB provided by .NET Core, there's no value in keeping this attribute.</span></span>
- <span data-ttu-id="cb641-112">`AccessibleObject` 클래스에서 `ComVisible(true)` 제거: 이러한 클래스는 CoCreateable(매개 변수가 없는 생성자가 없음)이 아니며, 이미 존재하는 인스턴스를 COM에 노출하는 경우 해당 특성이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-112">Removal of `ComVisible(true)` from `AccessibleObject` classes: The classes are not CoCreateable (they have no parameterless constructor), and exposing an already existing instance to COM does not require that attribute.</span></span>
- <span data-ttu-id="cb641-113">`Control` 및 `Component` 클래스에서 `ComVisible(true)` 제거: 이 특성은 예를 들어 VB6 또는 MFC에서 OLE/ActiveX를 통해 WinForms 컨트롤을 호스트하는 데 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-113">Removal of `ComVisible(true)` from `Control` and `Component` classes: This was used to allow hosting of WinForms controls via OLE/ActiveX, for example in VB6 or MFC.</span></span> <span data-ttu-id="cb641-114">그러나 이를 위해서는 더 이상 제공되지 않는 WinForms에 대한 TLB가 필요하고 기본적으로는 작동하지 않는 레지스트리 기반 활성화도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-114">However, this requires a TLB for WinForms, which is no longer provided, as well as registry-based activation, which also would not work out of the box.</span></span> <span data-ttu-id="cb641-115">일반적으로 WinForms 컨트롤의 COM 기반 호스팅은 유지 관리되지 않았으므로 이를 미지원 상태로 유지하는 대신 지원을 중단했습니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-115">Generally, there was no maintenance of COM-based hosting of WinForms controls, so support was removed instead of leaving it in an unsupported state.</span></span>
- <span data-ttu-id="cb641-116">컨트롤에서 `ClassInterface` 특성 제거: OLE/ActiveX를 통한 호스팅을 지원하지 않는 경우 이러한 특성은 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-116">Removal of `ClassInterface` attributes from controls: If hosting via OLE/ActiveX is not supported, these attributes aren't needed anymore.</span></span> <span data-ttu-id="cb641-117">이들은 개체가 여전히 COM에 노출되고 특성이 관련될 수 있는 다른 위치에서는 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-117">They are kept in other places where objects are still exposed to COM and the attribute may be relevant.</span></span>
- <span data-ttu-id="cb641-118">`EventArgs`에서 `ComVisible(true)` 제거: 이들은 주로 더 이상 지원되지 않는 OLE/ActiveX 호스팅에서 사용될 가능성이 높았습니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-118">Removal of `ComVisible(true)` from `EventArgs`: They were most likely used with OLE/ActiveX hosting, which is no longer supported.</span></span> <span data-ttu-id="cb641-119">CoCreateable도 아니므로 이 특성은 목적이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-119">They are not CoCreateable either, so the attribute has no purpose.</span></span> <span data-ttu-id="cb641-120">또한 TLB를 제공하지 않고 기존 인스턴스를 노출하는 것은 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-120">Also, exposing existing instances without providing a TLB makes no sense.</span></span>
- <span data-ttu-id="cb641-121">대리자에서 `ComVisible(true)` 제거: 용도를 알 수 없지만 WinForms 컨트롤의 ActiveX 호스팅이 더 이상 지원되지 않으므로 유용성이 없을 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-121">Removal of `ComVisible(true)` from delegates: Purpose is unknown, but since ActiveX hosting of WinForms Controls is no longer supported, it's unlikely to have any usefulness.</span></span>
- <span data-ttu-id="cb641-122">일부 공용이 아닌 코드에서 `ComVisible(true)` 제거: 잠재적 소비자는 새로운 Visual Studio 디자이너가 유일하지만 GUID를 지정하지 않으면 계속 필요할 가능성이 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-122">Removal of `ComVisible(true)` from some non-public code: The only potential consumer would be the new Visual Studio designer, but without a GUID specified, it's unlikely that it's still needed.</span></span>
- <span data-ttu-id="cb641-123">일부 임의 공용 디자이너 클래스에서 `ComVisible(true)` 제거: 이전 Visual Studio 디자이너가 COM interop을 사용하여 이러한 클래스와 통신해 왔을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-123">Removal of `ComVisible(true)` from some arbitrary public designer classes: The old Visual Studio designer may have been using COM interop to talk to these classes.</span></span> <span data-ttu-id="cb641-124">그러나 이전 디자이너는 .NET Core를 지원하지 않으므로 이들 클래스가 `ComVisible`이어야 하는 경우는 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-124">However, the old designer doesn't support .NET Core, so few people would need these as `ComVisible`.</span></span>
- <span data-ttu-id="cb641-125">`IWin32Window`는 .NET Framework에 정의된 것과 동일한 GUID를 정의했으며, 이는 위험한 결과를 초래합니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-125">`IWin32Window` defined the same GUID that was defined in .NET Framework, which has dangerous consequences.</span></span> <span data-ttu-id="cb641-126">.NET Framework 상호 운용성이 필요한 경우 `ComImport`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-126">If you require interop with .NET Framework, use `ComImport`.</span></span>
- <span data-ttu-id="cb641-127">WinForms 관리되는 `IDataObject`가 `ComVisible`이 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-127">The WinForms managed `IDataObject` was made `ComVisible`.</span></span> <span data-ttu-id="cb641-128">이는 필요하지 않으며 `IDataObject` COM interop에 대한 별도의 `ComImport` 인터페이스 선언이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-128">This is not required, there is a separate `ComImport` interface declaration for `IDataObject` COM interop.</span></span> <span data-ttu-id="cb641-129">TLB가 제공되지 않고 마샬링이 항상 실패하기 때문에 관리되는 `IDataObject`가 `ComVisible`이면 오히려 역효과가 일어납니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-129">It's counterproductive to have the managed `IDataObject` be `ComVisible`, since no TLB is provided and marshaling will always fail.</span></span> <span data-ttu-id="cb641-130">또한 GUID가 지정되지 않았고 .NET Framework와 달랐기 때문에 문서화되지 않은 IID를 제거해도 고객에게 부정적인 영향을 미칠 가능성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-130">Also, the GUID was not specified and differed from .NET Framework, so its unlikely that removing an undocumented IID will affect customers negatively.</span></span>
- <span data-ttu-id="cb641-131">`ComVisible(false)` 제거: 이들은 표면상 임의의 위치에 배치되며 클래스를 COM interop에 노출하는 것이 기본값이 아닌 경우 중복입니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-131">Removal of `ComVisible(false)`: Those are placed in seemingly arbitrary places and are redundant when the default is to not expose classes to COM interop.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="cb641-132">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="cb641-132">Version introduced</span></span>

<span data-ttu-id="cb641-133">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="cb641-133">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="cb641-134">권장 조치</span><span class="sxs-lookup"><span data-stu-id="cb641-134">Recommended action</span></span>

<span data-ttu-id="cb641-135">다음 예제는 .NET Framework 및 .NET Core 3.1에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-135">The following example works on .NET Framework and .NET Core 3.1.</span></span> <span data-ttu-id="cb641-136">이 예제는 JavaScript가 리플렉션을 통해 양식 하위 클래스로 콜백할 수 있도록 하는 .NET Framework 형식 라이브러리에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-136">This example relies on the .NET Framework type library, which allows the JavaScript to call back into the form subclass via reflection.</span></span>

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

<span data-ttu-id="cb641-137">이 예제가 .NET 5.0 이상 버전에서 작동하도록 할 수 있는 방법은 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-137">There are two possible ways to make the example work on .NET 5.0 and later versions:</span></span>

- <span data-ttu-id="cb641-138">프로젝트 수준에서 명시적으로 변경되지 않는 한 기본적으로 적용되는 `IDispatch`를 지원하는 사용자 선언 `ObjectForScripting` 개체를 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-138">Introduce a user-declared `ObjectForScripting` object that supports `IDispatch` (which is applied by default, unless changed explicitly at the project level).</span></span>

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

- <span data-ttu-id="cb641-139">노출할 메서드와의 인터페이스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="cb641-139">Declare an interface with the methods to expose.</span></span>

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

## <a name="affected-apis"></a><span data-ttu-id="cb641-140">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="cb641-140">Affected APIs</span></span>

<span data-ttu-id="cb641-141">모든 Windows Forms API.</span><span class="sxs-lookup"><span data-stu-id="cb641-141">All Windows Forms APIs.</span></span>

<!--

### Category

- Windows Forms

-->
