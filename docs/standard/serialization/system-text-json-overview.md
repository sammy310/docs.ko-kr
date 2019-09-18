---
title: .NET의 JSON serialization
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: 6cb45fded220b6123dbf4461f5f1cf1c3556ff69
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083091"
---
# <a name="json-serialization-in-net"></a><span data-ttu-id="dc2e8-102">.NET의 JSON serialization</span><span class="sxs-lookup"><span data-stu-id="dc2e8-102">JSON serialization in .NET</span></span>

<span data-ttu-id="dc2e8-103">네임 `System.Text.Json` 스페이스는 JavaScript Object Notation (JSON)로 serialize 하는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e8-103">The `System.Text.Json` namespace provides functionality for serializing to and from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="dc2e8-104">라이브러리 디자인은 광범위 한 기능 집합에 대 한 높은 성능 및 낮은 메모리 할당을 강조 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e8-104">The library design emphasizes high performance and low memory allocation over an extensive feature set.</span></span> <span data-ttu-id="dc2e8-105">UTF-8 지원은 UTF-8로 인코딩된 JSON 텍스트를 읽고 쓰는 프로세스를 최적화 합니다 .이는 웹의 데이터와 디스크의 파일에 대해 가장 널리 알려진 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e8-105">Built-in UTF-8 support optimizes the process of reading and writing JSON text encoded as UTF-8, which is the most prevalent encoding for data on the web and files on disk.</span></span>

<span data-ttu-id="dc2e8-106">또한 라이브러리는 메모리 내 DOM (문서 개체 모델)을 사용 하기 위한 클래스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e8-106">The library also provides classes for working with an in-memory document object model (DOM).</span></span> <span data-ttu-id="dc2e8-107">이 기능을 사용 하면 JSON 파일이 나 문자열의 요소에 대해 임의의 읽기 전용 액세스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e8-107">This feature enables random read-only access of the elements in a JSON file or string.</span></span> 

## <a name="how-to-get-the-library"></a><span data-ttu-id="dc2e8-108">라이브러리를 가져오는 방법</span><span class="sxs-lookup"><span data-stu-id="dc2e8-108">How to get the library</span></span>

* <span data-ttu-id="dc2e8-109">라이브러리는 [.Net Core 3.0](https://aka.ms/netcore3download) 공유 프레임 워크의 일부로 기본 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e8-109">The library is built-in as part of the [.NET Core 3.0](https://aka.ms/netcore3download) shared framework.</span></span>
* <span data-ttu-id="dc2e8-110">다른 대상 프레임 워크의 경우에는 [System.object](https://www.nuget.org/packages/System.Text.Json) NuGet 패키지를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e8-110">For other target frameworks, install the [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet package.</span></span> <span data-ttu-id="dc2e8-111">패키지는 다음을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e8-111">The package supports:</span></span>
  * <span data-ttu-id="dc2e8-112">.NET Standard 2.0 이상 버전</span><span class="sxs-lookup"><span data-stu-id="dc2e8-112">.NET Standard 2.0 and later versions</span></span>
  * <span data-ttu-id="dc2e8-113">.NET Framework 4.61 이상 버전</span><span class="sxs-lookup"><span data-stu-id="dc2e8-113">.NET Framework 4.61 and later versions</span></span>
  * <span data-ttu-id="dc2e8-114">.NET Core 2.0 이상 버전</span><span class="sxs-lookup"><span data-stu-id="dc2e8-114">.NET Core 2.0 and later versions</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dc2e8-115">추가 자료</span><span class="sxs-lookup"><span data-stu-id="dc2e8-115">Additional resources</span></span>

* [<span data-ttu-id="dc2e8-116">라이브러리를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="dc2e8-116">How to use the library</span></span>](system-text-json-how-to.md)
* [<span data-ttu-id="dc2e8-117">소스 코드</span><span class="sxs-lookup"><span data-stu-id="dc2e8-117">Source code</span></span>](https://github.com/dotnet/corefx/tree/master/src/System.Text.Json)
* [<span data-ttu-id="dc2e8-118">API 참조</span><span class="sxs-lookup"><span data-stu-id="dc2e8-118">API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="dc2e8-119">로드맵</span><span class="sxs-lookup"><span data-stu-id="dc2e8-119">Roadmap</span></span>](https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/roadmap/README.md)
* <span data-ttu-id="dc2e8-120">Dotnet/corefx 리포지토리의 GitHub 문제</span><span class="sxs-lookup"><span data-stu-id="dc2e8-120">GitHub issues in the dotnet/corefx repository</span></span>
  * [<span data-ttu-id="dc2e8-121">System.object의 개발에 대 한 토론</span><span class="sxs-lookup"><span data-stu-id="dc2e8-121">Discussion about the development of System.Text.Json</span></span>](https://github.com/dotnet/corefx/issues/33115)
  * [<span data-ttu-id="dc2e8-122">모든 System.web. Json 문제</span><span class="sxs-lookup"><span data-stu-id="dc2e8-122">All System.Text.Json issues</span></span>](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)
  * [<span data-ttu-id="dc2e8-123">Json 이라는 레이블이 지정 된 system.web 문제-doc</span><span class="sxs-lookup"><span data-stu-id="dc2e8-123">System.Text.Json issues labeled json-functionality-doc</span></span>](https://github.com/dotnet/corefx/labels/json-functionality-doc)
