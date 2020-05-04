---
title: 확장
ms.date: 12/13/2019
description: SQLite 확장을 로드하는 방법을 알아봅니다.
ms.openlocfilehash: 51c705349c25240fe42e0edda8004a3e3b013ca3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242961"
---
# <a name="extensions"></a><span data-ttu-id="16767-103">확장</span><span class="sxs-lookup"><span data-stu-id="16767-103">Extensions</span></span>

<span data-ttu-id="16767-104">SQLite는 런타임 시 확장 로드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="16767-104">SQLite supports loading extensions at run time.</span></span> <span data-ttu-id="16767-105">확장에는 추가 SQL 함수, 데이터 정렬, 가상 테이블 등과 같은 항목이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="16767-105">Extensions include things like additional SQL functions, collations, virtual tables, and more.</span></span>

<span data-ttu-id="16767-106">.NET Core에는 참조된 NuGet 패키지와 같은 추가 위치에서 네이티브 라이브러리를 찾기 위한 추가 논리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="16767-106">.NET Core includes additional logic for locating native libraries in additional places like referenced NuGet packages.</span></span> <span data-ttu-id="16767-107">아쉽지만 SQLite는 이 논리를 활용할 수 없습니다. 플랫폼 API를 직접 호출하여 라이브러리를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="16767-107">Unfortunately, SQLite can't leverage this logic; it calls the platform API directly to load libraries.</span></span> <span data-ttu-id="16767-108">따라서 SQLite 확장을 로드하기 전에 PATH, LD_LIBRARY_PATH 또는 DYLD_LIBRARY_PATH 환경 변수를 수정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16767-108">Because of this, you may need to modify the PATH, LD_LIBRARY_PATH, or DYLD_LIBRARY_PATH environment variables before loading SQLite extensions.</span></span> <span data-ttu-id="16767-109">참조된 NuGet 패키지 내에서 현재 런타임의 이진 파일을 찾는 것을 보여 주는 [샘플](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs)은 GitHub에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16767-109">There's [a sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) on GitHub that demonstrates finding binaries for the current runtime inside a referenced NuGet package.</span></span>

<span data-ttu-id="16767-110">확장을 로드하려면 <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="16767-110">To load an extension, call the <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> method.</span></span> <span data-ttu-id="16767-111">연결을 닫았다가 다시 열더라도 Microsoft.Data.Sqlite가 확장을 로드된 상태로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="16767-111">Microsoft.Data.Sqlite will ensure that the extension remains loaded even if the connection is closed and reopened.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a><span data-ttu-id="16767-112">참조</span><span class="sxs-lookup"><span data-stu-id="16767-112">See also</span></span>

* [<span data-ttu-id="16767-113">런타임 로드 가능한 확장</span><span class="sxs-lookup"><span data-stu-id="16767-113">Run-Time Loadable Extensions</span></span>](https://www.sqlite.org/loadext.html)
