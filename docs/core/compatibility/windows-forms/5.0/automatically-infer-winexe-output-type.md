---
title: '호환성이 손상되는 변경: WPF 및 WinForms 앱에 대해 OutputType이 WinExe로 설정됨'
description: Windows Forms 앱에 대해 OutputType이 WinExe로 자동으로 설정되는 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 09/18/2020
ms.openlocfilehash: 072c5b11c8304eb540e176ce9747930789f28505
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760020"
---
# <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a><span data-ttu-id="41f99-103">WPF 및 WinForms 앱에 대해 OutputType이 WinExe로 설정됨</span><span class="sxs-lookup"><span data-stu-id="41f99-103">OutputType set to WinExe for WPF and WinForms apps</span></span>

<span data-ttu-id="41f99-104">WPF(Windows Presentation Foundation) 및 Windows Forms 앱에 대해 `OutputType`은 자동으로 `WinExe`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="41f99-104">`OutputType` is automatically set to `WinExe` for Windows Presentation Foundation (WPF) and Windows Forms apps.</span></span> <span data-ttu-id="41f99-105">`OutputType`이 `WinExe`로 설정되면 앱 실행 시 콘솔 창이 열리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41f99-105">When `OutputType` is set to `WinExe`, a console window doesn't open when the app is executed.</span></span>

## <a name="change-description"></a><span data-ttu-id="41f99-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="41f99-106">Change description</span></span>

<span data-ttu-id="41f99-107">이전 버전의 .NET에서는 프로젝트 파일에 `OutputType`에 대해 지정된 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="41f99-107">In previous versions of .NET, the value that's specified for `OutputType` in the project file is used.</span></span> <span data-ttu-id="41f99-108">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="41f99-108">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="41f99-109">.NET 5.0부터 `OutputType`은 WPF 및 Windows Forms 앱에 대해 자동으로 `WinExe`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="41f99-109">Starting in .NET 5.0, `OutputType` is automatically set to `WinExe` for WPF and Windows Forms apps.</span></span> <span data-ttu-id="41f99-110">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="41f99-110">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>WinExe</OutputType>
</PropertyGroup>
```

## <a name="reason-for-change"></a><span data-ttu-id="41f99-111">변경 이유</span><span class="sxs-lookup"><span data-stu-id="41f99-111">Reason for change</span></span>

<span data-ttu-id="41f99-112">대부분 사용자가 WPF 또는 Windows Forms 앱 실행 시 콘솔 창이 열리기를 원하지 않는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="41f99-112">It's assumed that most users don't want a console window to open when a WPF or Windows Forms app is executed.</span></span> <span data-ttu-id="41f99-113">또한 [이제 이러한 애플리케이션 유형에 .NET SDK를 사용](sdk-and-target-framework-change.md)(Windows 데스크톱 SDK 아님)하므로 올바른 기본값이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="41f99-113">In addition, [now that these application types use the .NET SDK](sdk-and-target-framework-change.md) instead of the Windows Desktop SDK, the correct default will be set.</span></span> <span data-ttu-id="41f99-114">또한 iOS 및 Android 대상 지정을 위한 지원이 추가되면 동일한 출력 형식이 사용되는 경우 여러 플랫폼 사이에 멀티 타기팅하기가 더 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="41f99-114">Further, when support for targeting iOS and Android is added, it will be easier to multi-target between multiple platforms if they all use the same output type.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="41f99-115">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="41f99-115">Version introduced</span></span>

<span data-ttu-id="41f99-116">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="41f99-116">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="41f99-117">권장 조치</span><span class="sxs-lookup"><span data-stu-id="41f99-117">Recommended action</span></span>

<span data-ttu-id="41f99-118">아무 작업도 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41f99-118">No action is required in your part.</span></span> <span data-ttu-id="41f99-119">하지만 이전 동작으로 되돌리려면 프로젝트 파일에서 `DisableWinExeOutputInference` 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="41f99-119">However, if you want to revert to the old behavior, set the `DisableWinExeOutputInference` property to `true` in your project file.</span></span>

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

## <a name="affected-apis"></a><span data-ttu-id="41f99-120">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="41f99-120">Affected APIs</span></span>

<span data-ttu-id="41f99-121">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41f99-121">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
