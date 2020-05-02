---
title: Xamarin 제한 사항
ms.date: 12/13/2019
description: Xamarin을 사용할 때 발생할 수 있는 몇 가지 제한 사항에 대해 설명합니다.
ms.openlocfilehash: 192f25954726919dc66d706e755e0853404b4d85
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450407"
---
# <a name="xamarin-limitations"></a><span data-ttu-id="aee0b-103">Xamarin 제한 사항</span><span class="sxs-lookup"><span data-stu-id="aee0b-103">Xamarin limitations</span></span>

<span data-ttu-id="aee0b-104">Microsoft.Data.Sqlite는 .NET Standard 2.0을 대상으로 하며 Xamarin에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="aee0b-104">Microsoft.Data.Sqlite targets .NET Standard 2.0 and is supported on Xamarin.</span></span> <span data-ttu-id="aee0b-105">다음 표에서는 기본 SQLitePCLRaw 번들이 네이티브 SQLite 이진 파일을 제공하는 플랫폼을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="aee0b-105">The following table shows which platforms the default SQLitePCLRaw bundle provides native SQLite binaries for.</span></span> <span data-ttu-id="aee0b-106">다른 번들을 사용하거나 고유한 네이티브 SQLite 이진 파일을 제공하는 방법에 대한 자세한 내용은 [사용자 지정 SQLite 버전](custom-versions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aee0b-106">See [Custom SQLite versions](custom-versions.md) for details on using a different bundle or providing your own native SQLite binaries.</span></span>

| <span data-ttu-id="aee0b-107">플랫폼</span><span class="sxs-lookup"><span data-stu-id="aee0b-107">Platform</span></span> | <span data-ttu-id="aee0b-108">SQLite 이진 파일</span><span class="sxs-lookup"><span data-stu-id="aee0b-108">SQLite binaries</span></span> |
| --- | --- |
| <span data-ttu-id="aee0b-109">**Xamarin.Android**</span><span class="sxs-lookup"><span data-stu-id="aee0b-109">**Xamarin.Android**</span></span> | <span data-ttu-id="aee0b-110">—</span><span class="sxs-lookup"><span data-stu-id="aee0b-110">—</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64-v8a` | <span data-ttu-id="aee0b-111">✔</span><span class="sxs-lookup"><span data-stu-id="aee0b-111">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`armeabi-v7a` | <span data-ttu-id="aee0b-112">✔</span><span class="sxs-lookup"><span data-stu-id="aee0b-112">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | <span data-ttu-id="aee0b-113">✔</span><span class="sxs-lookup"><span data-stu-id="aee0b-113">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86_64` | <span data-ttu-id="aee0b-114">✔</span><span class="sxs-lookup"><span data-stu-id="aee0b-114">✔</span></span> |
| <span data-ttu-id="aee0b-115">**Xamarin.iOS**</span><span class="sxs-lookup"><span data-stu-id="aee0b-115">**Xamarin.iOS**</span></span> | <span data-ttu-id="aee0b-116">✔</span><span class="sxs-lookup"><span data-stu-id="aee0b-116">✔</span></span> |
| <span data-ttu-id="aee0b-117">**Xamarin.Mac**</span><span class="sxs-lookup"><span data-stu-id="aee0b-117">**Xamarin.Mac**</span></span> | <span data-ttu-id="aee0b-118">✔</span><span class="sxs-lookup"><span data-stu-id="aee0b-118">✔</span></span> |
| <span data-ttu-id="aee0b-119">**Xamarin.TVOS**</span><span class="sxs-lookup"><span data-stu-id="aee0b-119">**Xamarin.TVOS**</span></span> | <span data-ttu-id="aee0b-120">✔</span><span class="sxs-lookup"><span data-stu-id="aee0b-120">✔</span></span> |
| <span data-ttu-id="aee0b-121">**UWP**</span><span class="sxs-lookup"><span data-stu-id="aee0b-121">**UWP**</span></span> | <span data-ttu-id="aee0b-122">—</span><span class="sxs-lookup"><span data-stu-id="aee0b-122">—</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm` | <span data-ttu-id="aee0b-123">✔</span><span class="sxs-lookup"><span data-stu-id="aee0b-123">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64` | <span data-ttu-id="aee0b-124">✔</span><span class="sxs-lookup"><span data-stu-id="aee0b-124">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x64` | <span data-ttu-id="aee0b-125">✔</span><span class="sxs-lookup"><span data-stu-id="aee0b-125">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | <span data-ttu-id="aee0b-126">✔</span><span class="sxs-lookup"><span data-stu-id="aee0b-126">✔</span></span> |

## <a name="ios"></a><span data-ttu-id="aee0b-127">iOS</span><span class="sxs-lookup"><span data-stu-id="aee0b-127">iOS</span></span>

<span data-ttu-id="aee0b-128">Microsoft.Data.Sqlite는 SQLitePCLRaw 번들을 자동으로 초기화하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee0b-128">Microsoft.Data.Sqlite tries to automatically initialize SQLitePCLRaw bundles.</span></span> <span data-ttu-id="aee0b-129">불행하게도 Xamarin.iOS에 대한 AOT(ahead-of-time) 컴파일의 제한 사항으로 인해 시도는 실패하고 다음과 같은 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="aee0b-129">Unfortunately, because of limitations in the ahead-of-time (AOT) compilation for Xamarin.iOS, the attempt fails and you get the following error.</span></span>

> <span data-ttu-id="aee0b-130">`SQLitePCL.raw.SetProvider()`를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee0b-130">You need to call `SQLitePCL.raw.SetProvider()`.</span></span> <span data-ttu-id="aee0b-131">번들 패키지를 사용하는 경우 `SQLitePCL.Batteries.Init()`를 호출하여 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="aee0b-131">If you're using a bundle package, this is done by calling `SQLitePCL.Batteries.Init()`.</span></span>

<span data-ttu-id="aee0b-132">번들을 초기화하려면 Microsoft.Data.Sqlite를 사용하기 전에 앱에 다음 코드 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="aee0b-132">To initialize the bundle, add the following line of code to your app before using Microsoft.Data.Sqlite.</span></span>

```csharp
SQLitePCL.Batteries_V2.Init();
```

## <a name="see-also"></a><span data-ttu-id="aee0b-133">참조</span><span class="sxs-lookup"><span data-stu-id="aee0b-133">See also</span></span>

* [<span data-ttu-id="aee0b-134">비동기 제한 사항</span><span class="sxs-lookup"><span data-stu-id="aee0b-134">Async limitations</span></span>](async.md)
* [<span data-ttu-id="aee0b-135">사용자 지정 SQLite 버전</span><span class="sxs-lookup"><span data-stu-id="aee0b-135">Custom SQLite versions</span></span>](custom-versions.md)
