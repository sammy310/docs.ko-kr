---
ms.openlocfilehash: 4b5c886ad35afbbf0a68e03b3174ab9ea1f5524f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614767"
---
### <a name="cspparametersparentwindowhandle-now-expects-hwnd-value"></a><span data-ttu-id="edbf8-101">이제 CspParameters.ParentWindowHandle에 HWND 값 필요</span><span class="sxs-lookup"><span data-stu-id="edbf8-101">CspParameters.ParentWindowHandle now expects HWND value</span></span>

#### <a name="details"></a><span data-ttu-id="edbf8-102">설명</span><span class="sxs-lookup"><span data-stu-id="edbf8-102">Details</span></span>

<span data-ttu-id="edbf8-103">.NET Framework 2.0에 도입된 <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> 값을 사용하면 애플리케이션에서 키에 액세스하는 데 필요한 UI(PIN 프롬프트 또는 동의 대화 상자)가 지정된 창에 대한 모달 자식 항목으로 열리도록 부모 창 핸들 값을 등록할 수 있습니다. .NET Framework 4.7을 대상으로 하는 앱부터 Windows Forms 애플리케이션은 다음과 같은 코드로 <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edbf8-103">The <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> value, introduced in .NET Framework 2.0, allows an application to register a parent window handle value such that any UI required to access the key (such as a PIN prompt or consent dialog) opens as a modal child to the specified window.Starting with apps that target the .NET Framework 4.7, a Windows Forms application can set the <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> property with code like the following:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
```

<span data-ttu-id="edbf8-104">이전 버전의 .NET Framework에서 값은 [HWND](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types#HWND) 값이 있던 메모리의 위치를 나타내는 <xref:System.IntPtr?displayProperty=fullName>가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="edbf8-104">In previous versions of the .NET Framework, the value was expected to be an <xref:System.IntPtr?displayProperty=fullName> representing a location in memory where the [HWND](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types#HWND) value resided.</span></span> <span data-ttu-id="edbf8-105">Windows 7 이전 버전에서 이 속성을 form.Handle로 설정해도 아무 영향이 없지만, Windows 8 이상 버전에서는 &quot;<xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>: 매개 변수가 잘못되었습니다.&quot;라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="edbf8-105">Setting the property to form.Handle on Windows 7 and earlier versions had no effect, but on Windows 8 and later versions, it results in a &quot;<xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>: The parameter is incorrect.&quot;</span></span>

#### <a name="suggestion"></a><span data-ttu-id="edbf8-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="edbf8-106">Suggestion</span></span>

<span data-ttu-id="edbf8-107">부모 창 관계를 등록하려는 .NET Framework 4.7 이상을 대상으로 하는 애플리케이션에서는 다음과 같은 간단한 형식을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="edbf8-107">Applications targeting .NET Framework 4.7 or higher wishing to register a parent window relationship are encouraged to use the simplified form:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
```

<span data-ttu-id="edbf8-108">통과시킬 올바른 값이 `form.Handle` 값을 가졌던 메모리 위치의 주소임을 확인한 사용자는 AppContext 스위치 `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle`를 `true`로 설정하여 동작 변경을 옵트아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edbf8-108">Users who had identified that the correct value to pass was the address of a memory location which held the value `form.Handle` can opt out of the behavior change by setting the AppContext switch `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` to `true`:</span></span>

- <span data-ttu-id="edbf8-109">[여기](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46)에 설명된 대로 AppContext에서 compat 스위치를 프로그래밍 방식으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="edbf8-109">By programmatically setting compat switches on the AppContext, as explained [here](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</span></span>
- <span data-ttu-id="edbf8-110">다음 줄을 app.config 파일의 `<runtime>` 섹션에 추가</span><span class="sxs-lookup"><span data-stu-id="edbf8-110">By adding the following line to the `<runtime>` section of the app.config file:</span></span>

```xml
<runtime>
 <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
</runtime>
```

<span data-ttu-id="edbf8-111">반대로 이전 버전의 .NET Framework에서 애플리케이션이 로드될 때 .NET Framework 4.7 런타임에서 새로운 동작을 옵트인하려는 사용자는 AppContext 스위치를 `false`로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edbf8-111">Conversely, users who wish to opt in to the new behavior on the .NET Framework 4.7 runtime when the application loads under older .NET Framework versions can set the AppContext switch to `false`.</span></span>

| <span data-ttu-id="edbf8-112">이름</span><span class="sxs-lookup"><span data-stu-id="edbf8-112">Name</span></span>    | <span data-ttu-id="edbf8-113">값</span><span class="sxs-lookup"><span data-stu-id="edbf8-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="edbf8-114">Scope</span><span class="sxs-lookup"><span data-stu-id="edbf8-114">Scope</span></span>   | <span data-ttu-id="edbf8-115">부</span><span class="sxs-lookup"><span data-stu-id="edbf8-115">Minor</span></span>       |
| <span data-ttu-id="edbf8-116">버전</span><span class="sxs-lookup"><span data-stu-id="edbf8-116">Version</span></span> | <span data-ttu-id="edbf8-117">4.7</span><span class="sxs-lookup"><span data-stu-id="edbf8-117">4.7</span></span>         |
| <span data-ttu-id="edbf8-118">형식</span><span class="sxs-lookup"><span data-stu-id="edbf8-118">Type</span></span>    | <span data-ttu-id="edbf8-119">대상 변경</span><span class="sxs-lookup"><span data-stu-id="edbf8-119">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="edbf8-120">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="edbf8-120">Affected APIs</span></span>

- <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle?displayProperty=nameWithType>
