---
title: 확장명
ms.date: 12/13/2019
description: SQLite 확장을 로드 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: a85b1227be4274dd20156d2475d6d2d68e250f99
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901292"
---
# <a name="extensions"></a><span data-ttu-id="a5247-103">확장명</span><span class="sxs-lookup"><span data-stu-id="a5247-103">Extensions</span></span>

<span data-ttu-id="a5247-104">SQLite는 런타임에 확장 로드를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5247-104">SQLite supports loading extensions at run time.</span></span> <span data-ttu-id="a5247-105">확장에는 추가 SQL 함수, 데이터 정렬, 가상 테이블 등과 같은 항목이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5247-105">Extensions include things like additional SQL functions, collations, virtual tables, and more.</span></span>

<span data-ttu-id="a5247-106">.NET Core에는 참조 된 NuGet 패키지와 같은 추가 위치에서 네이티브 라이브러리를 찾기 위한 추가 논리가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5247-106">.NET Core includes additional logic for locating native libraries in additional places like referenced NuGet packages.</span></span> <span data-ttu-id="a5247-107">아쉽게도 SQLite는이 논리를 활용할 수 없습니다. 플랫폼 API를 직접 호출 하 여 라이브러리를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5247-107">Unfortunately, SQLite can't leverage this logic; it calls the platform API directly to load libraries.</span></span> <span data-ttu-id="a5247-108">따라서 SQLite 확장을 로드 하기 전에 PATH, LD_LIBRARY_PATH 또는 DYLD_LIBRARY_PATH 환경 변수를 수정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5247-108">Because of this, you may need to modify the PATH, LD_LIBRARY_PATH, or DYLD_LIBRARY_PATH environment variables before loading SQLite extensions.</span></span> <span data-ttu-id="a5247-109">참조 된 NuGet 패키지 내에서 현재 런타임에 대 한 이진 파일 찾기를 보여 주는 [샘플은](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) GitHub에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5247-109">There's [a sample](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) on GitHub that demonstrates finding binaries for the current runtime inside a referenced NuGet package.</span></span>

<span data-ttu-id="a5247-110">확장을 로드 하려면 <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5247-110">To load an extension, call the <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> method.</span></span> <span data-ttu-id="a5247-111">연결을 닫았다가 다시 열면 확장이 로드 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5247-111">Microsoft.Data.Sqlite will ensure that the extension remains loaded even if the connection is closed and reopened.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a><span data-ttu-id="a5247-112">참조</span><span class="sxs-lookup"><span data-stu-id="a5247-112">See also</span></span>

* [<span data-ttu-id="a5247-113">런타임 로드 가능한 확장</span><span class="sxs-lookup"><span data-stu-id="a5247-113">Run-Time Loadable Extensions</span></span>](https://www.sqlite.org/loadext.html)
