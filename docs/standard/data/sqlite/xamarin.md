---
title: Xamarin 제한 사항
ms.date: 12/13/2019
description: Xamarin을 사용할 때 발생 하는 몇 가지 제한 사항에 대해 설명 합니다.
ms.openlocfilehash: 192f25954726919dc66d706e755e0853404b4d85
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450407"
---
# <a name="xamarin-limitations"></a><span data-ttu-id="a7409-103">Xamarin 제한 사항</span><span class="sxs-lookup"><span data-stu-id="a7409-103">Xamarin limitations</span></span>

<span data-ttu-id="a7409-104">Microsoft. Sqlite 대상은 .NET Standard 2.0 이며 Xamarin에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7409-104">Microsoft.Data.Sqlite targets .NET Standard 2.0 and is supported on Xamarin.</span></span> <span data-ttu-id="a7409-105">다음 표에서는 기본 SQLitePCLRaw 번들이에 대 한 기본 SQLite 이진 파일을 제공 하는 플랫폼을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7409-105">The following table shows which platforms the default SQLitePCLRaw bundle provides native SQLite binaries for.</span></span> <span data-ttu-id="a7409-106">다른 번들 사용 또는 고유한 기본 SQLite 이진 파일 제공에 대 한 자세한 내용은 [사용자 지정 sqlite 버전](custom-versions.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a7409-106">See [Custom SQLite versions](custom-versions.md) for details on using a different bundle or providing your own native SQLite binaries.</span></span>

| <span data-ttu-id="a7409-107">Platform</span><span class="sxs-lookup"><span data-stu-id="a7409-107">Platform</span></span> | <span data-ttu-id="a7409-108">SQLite 이진 파일</span><span class="sxs-lookup"><span data-stu-id="a7409-108">SQLite binaries</span></span> |
| --- | --- |
| <span data-ttu-id="a7409-109">**Xamarin.Android**</span><span class="sxs-lookup"><span data-stu-id="a7409-109">**Xamarin.Android**</span></span> | <span data-ttu-id="a7409-110">—</span><span class="sxs-lookup"><span data-stu-id="a7409-110">—</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64-v8a` | <span data-ttu-id="a7409-111">✔</span><span class="sxs-lookup"><span data-stu-id="a7409-111">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`armeabi-v7a` | <span data-ttu-id="a7409-112">✔</span><span class="sxs-lookup"><span data-stu-id="a7409-112">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | <span data-ttu-id="a7409-113">✔</span><span class="sxs-lookup"><span data-stu-id="a7409-113">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86_64` | <span data-ttu-id="a7409-114">✔</span><span class="sxs-lookup"><span data-stu-id="a7409-114">✔</span></span> |
| <span data-ttu-id="a7409-115">**Xamarin.iOS**</span><span class="sxs-lookup"><span data-stu-id="a7409-115">**Xamarin.iOS**</span></span> | <span data-ttu-id="a7409-116">✔</span><span class="sxs-lookup"><span data-stu-id="a7409-116">✔</span></span> |
| <span data-ttu-id="a7409-117">**Xamarin.Mac**</span><span class="sxs-lookup"><span data-stu-id="a7409-117">**Xamarin.Mac**</span></span> | <span data-ttu-id="a7409-118">✔</span><span class="sxs-lookup"><span data-stu-id="a7409-118">✔</span></span> |
| <span data-ttu-id="a7409-119">**TVOS**</span><span class="sxs-lookup"><span data-stu-id="a7409-119">**Xamarin.TVOS**</span></span> | <span data-ttu-id="a7409-120">✔</span><span class="sxs-lookup"><span data-stu-id="a7409-120">✔</span></span> |
| <span data-ttu-id="a7409-121">**UWP**</span><span class="sxs-lookup"><span data-stu-id="a7409-121">**UWP**</span></span> | <span data-ttu-id="a7409-122">—</span><span class="sxs-lookup"><span data-stu-id="a7409-122">—</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm` | <span data-ttu-id="a7409-123">✔</span><span class="sxs-lookup"><span data-stu-id="a7409-123">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64` | <span data-ttu-id="a7409-124">✔</span><span class="sxs-lookup"><span data-stu-id="a7409-124">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x64` | <span data-ttu-id="a7409-125">✔</span><span class="sxs-lookup"><span data-stu-id="a7409-125">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | <span data-ttu-id="a7409-126">✔</span><span class="sxs-lookup"><span data-stu-id="a7409-126">✔</span></span> |

## <a name="ios"></a><span data-ttu-id="a7409-127">iOS</span><span class="sxs-lookup"><span data-stu-id="a7409-127">iOS</span></span>

<span data-ttu-id="a7409-128">SQLitePCLRaw 번들을 자동으로 초기화 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7409-128">Microsoft.Data.Sqlite tries to automatically initialize SQLitePCLRaw bundles.</span></span> <span data-ttu-id="a7409-129">불행 하 게 Xamarin.ios에 대 한 AOT (사전) 컴파일의 제한 사항으로 인해 시도는 실패 하 고 다음과 같은 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7409-129">Unfortunately, because of limitations in the ahead-of-time (AOT) compilation for Xamarin.iOS, the attempt fails and you get the following error.</span></span>

> <span data-ttu-id="a7409-130">`SQLitePCL.raw.SetProvider()`를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7409-130">You need to call `SQLitePCL.raw.SetProvider()`.</span></span> <span data-ttu-id="a7409-131">번들 패키지를 사용 하는 경우 `SQLitePCL.Batteries.Init()`를 호출 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7409-131">If you're using a bundle package, this is done by calling `SQLitePCL.Batteries.Init()`.</span></span>

<span data-ttu-id="a7409-132">번들을 초기화 하려면 Microsoft. Sqlite를 사용 하기 전에 앱에 다음 코드 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7409-132">To initialize the bundle, add the following line of code to your app before using Microsoft.Data.Sqlite.</span></span>

```csharp
SQLitePCL.Batteries_V2.Init();
```

## <a name="see-also"></a><span data-ttu-id="a7409-133">참조</span><span class="sxs-lookup"><span data-stu-id="a7409-133">See also</span></span>

* [<span data-ttu-id="a7409-134">비동기 제한 사항</span><span class="sxs-lookup"><span data-stu-id="a7409-134">Async limitations</span></span>](async.md)
* [<span data-ttu-id="a7409-135">사용자 지정 SQLite 버전</span><span class="sxs-lookup"><span data-stu-id="a7409-135">Custom SQLite versions</span></span>](custom-versions.md)
