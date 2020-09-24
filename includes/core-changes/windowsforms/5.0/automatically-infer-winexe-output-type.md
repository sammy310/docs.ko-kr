---
ms.openlocfilehash: 54bee14f6de409550357194e905b6ee5d8ef8f18
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679003"
---
### <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a><span data-ttu-id="cf45d-101">WPF 및 WinForms 앱에 대해 OutputType이 WinExe로 설정됨</span><span class="sxs-lookup"><span data-stu-id="cf45d-101">OutputType set to WinExe for WPF and WinForms apps</span></span>

<span data-ttu-id="cf45d-102">WPF(Windows Presentation Foundation) 및 Windows Forms 앱에 대해 `OutputType`은 자동으로 `WinExe`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf45d-102">`OutputType` is automatically set to `WinExe` for Windows Presentation Foundation (WPF) and Windows Forms apps.</span></span> <span data-ttu-id="cf45d-103">`OutputType`이 `WinExe`로 설정되면 앱 실행 시 콘솔 창이 열리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf45d-103">When `OutputType` is set to `WinExe`, a console window doesn't open when the app is executed.</span></span>

#### <a name="change-description"></a><span data-ttu-id="cf45d-104">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="cf45d-104">Change description</span></span>

<span data-ttu-id="cf45d-105">이전 버전의 .NET에서는 프로젝트 파일에 `OutputType`에 대해 지정된 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf45d-105">In previous versions of .NET, the value that's specified for `OutputType` in the project file is used.</span></span> <span data-ttu-id="cf45d-106">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf45d-106">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="cf45d-107">.NET 5.0부터 `OutputType`은 WPF 및 Windows Forms 앱에 대해 자동으로 `WinExe`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf45d-107">Starting in .NET 5.0, `OutputType` is automatically set to `WinExe` for WPF and Windows Forms apps.</span></span> <span data-ttu-id="cf45d-108">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf45d-108">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>WinExe</OutputType>
</PropertyGroup>
```

#### <a name="reason-for-change"></a><span data-ttu-id="cf45d-109">변경 이유</span><span class="sxs-lookup"><span data-stu-id="cf45d-109">Reason for change</span></span>

<span data-ttu-id="cf45d-110">대부분 사용자가 WPF 또는 Windows Forms 앱 실행 시 콘솔 창이 열리기를 원하지 않는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="cf45d-110">It's assumed that most users don't want a console window to open when a WPF or Windows Forms app is executed.</span></span> <span data-ttu-id="cf45d-111">또한 [이제 이러한 애플리케이션 유형에 .NET SDK를 사용](../../../../docs/core/compatibility/wpf.md#winforms-and-wpf-apps-use-microsoftnetsdk)(Windows 데스크톱 SDK 아님)하므로 올바른 기본값이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf45d-111">In addition, [now that these application types use the .NET SDK](../../../../docs/core/compatibility/wpf.md#winforms-and-wpf-apps-use-microsoftnetsdk) instead of the Windows Desktop SDK, the correct default will be set.</span></span> <span data-ttu-id="cf45d-112">또한 iOS 및 Android 대상 지정을 위한 지원이 추가되면 동일한 출력 형식이 사용되는 경우 여러 플랫폼 사이에 멀티 타기팅하기가 더 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="cf45d-112">Further, when support for targeting iOS and Android is added, it will be easier to multi-target between multiple platforms if they all use the same output type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cf45d-113">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="cf45d-113">Version introduced</span></span>

<span data-ttu-id="cf45d-114">.NET 5.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="cf45d-114">.NET 5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cf45d-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="cf45d-115">Recommended action</span></span>

<span data-ttu-id="cf45d-116">아무 작업도 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf45d-116">No action is required in your part.</span></span> <span data-ttu-id="cf45d-117">하지만 이전 동작으로 되돌리려면 프로젝트 파일에서 `DisableWinExeOutputInference` 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cf45d-117">However, if you want to revert to the old behavior, set the `DisableWinExeOutputInference` property to `true` in your project file.</span></span>

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

#### <a name="category"></a><span data-ttu-id="cf45d-118">범주</span><span class="sxs-lookup"><span data-stu-id="cf45d-118">Category</span></span>

- <span data-ttu-id="cf45d-119">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cf45d-119">Windows Forms</span></span>
- <span data-ttu-id="cf45d-120">WPF(Windows Presentation Framework)</span><span class="sxs-lookup"><span data-stu-id="cf45d-120">Windows Presentation Framework (WPF)</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cf45d-121">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="cf45d-121">Affected APIs</span></span>

<span data-ttu-id="cf45d-122">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf45d-122">Not detectable via API analysis.</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
