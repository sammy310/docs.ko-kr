---
title: Collation
ms.date: 12/13/2019
description: 사용자 지정 정렬 순서를 만드는 방법에 대해 알아봅니다.
ms.openlocfilehash: 9cc574a75c8f5347dd9bb44e36af72e50afa57b4
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777380"
---
# <a name="collation"></a><span data-ttu-id="dcbdf-103">Collation</span><span class="sxs-lookup"><span data-stu-id="dcbdf-103">Collation</span></span>

<span data-ttu-id="dcbdf-104">데이터 정렬 순서는 SQLite에서 텍스트 값을 비교 하 여 순서 및 같음을 결정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcbdf-104">Collating sequences are used by SQLite when comparing TEXT values to determine order and equality.</span></span> <span data-ttu-id="dcbdf-105">SQL 쿼리에서 열 또는 작업당 작업을 만들 때 사용할 데이터 정렬을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbdf-105">You can specify which collation to use when creating columns or per-operation in SQL queries.</span></span> <span data-ttu-id="dcbdf-106">SQLite에는 기본적으로 세 가지 데이터 정렬 순서가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcbdf-106">SQLite includes three collating sequences by default.</span></span>

| <span data-ttu-id="dcbdf-107">Collation</span><span class="sxs-lookup"><span data-stu-id="dcbdf-107">Collation</span></span> | <span data-ttu-id="dcbdf-108">설명</span><span class="sxs-lookup"><span data-stu-id="dcbdf-108">Description</span></span>                               |
| --------- | ----------------------------------------- |
| <span data-ttu-id="dcbdf-109">RTRIM</span><span class="sxs-lookup"><span data-stu-id="dcbdf-109">RTRIM</span></span>     | <span data-ttu-id="dcbdf-110">후행 공백을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbdf-110">Ignores trailing whitespace</span></span>               |
| <span data-ttu-id="dcbdf-111">NOCASE</span><span class="sxs-lookup"><span data-stu-id="dcbdf-111">NOCASE</span></span>    | <span data-ttu-id="dcbdf-112">ASCII 문자 a-z의 대/소문자 구분 안 함</span><span class="sxs-lookup"><span data-stu-id="dcbdf-112">Case-insensitive for ASCII characters A-Z</span></span> |
| <span data-ttu-id="dcbdf-113">BINARY</span><span class="sxs-lookup"><span data-stu-id="dcbdf-113">BINARY</span></span>    | <span data-ttu-id="dcbdf-114">대/소문자 구분</span><span class="sxs-lookup"><span data-stu-id="dcbdf-114">Case-sensitive.</span></span> <span data-ttu-id="dcbdf-115">바이트 직접 비교</span><span class="sxs-lookup"><span data-stu-id="dcbdf-115">Compares bytes directly</span></span>   |

## <a name="custom-collation"></a><span data-ttu-id="dcbdf-116">사용자 지정 데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="dcbdf-116">Custom collation</span></span>

<span data-ttu-id="dcbdf-117">사용자 고유의 데이터 정렬 시퀀스를 정의 하거나 <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>를 사용 하 여 기본 제공 되는 시퀀스를 재정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbdf-117">You can also define your own collating sequences or override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span></span> <span data-ttu-id="dcbdf-118">다음 예에서는 유니코드 문자를 지원 하도록 NOCASE 데이터 정렬을 재정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dcbdf-118">The following example shows overriding the NOCASE collation to support Unicode characters.</span></span> <span data-ttu-id="dcbdf-119">[전체 샘플 코드](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs) 는 GitHub에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbdf-119">The [full sample code](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs) is available on GitHub.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a><span data-ttu-id="dcbdf-120">Like 연산자</span><span class="sxs-lookup"><span data-stu-id="dcbdf-120">Like operator</span></span>

<span data-ttu-id="dcbdf-121">SQLite의 LIKE 연산자는 데이터 정렬을 인식 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbdf-121">The LIKE operator in SQLite doesn't honor collations.</span></span> <span data-ttu-id="dcbdf-122">기본 구현에는 NOCASE 데이터 정렬과 동일한 의미 체계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbdf-122">The default implementation has the same semantics as the NOCASE collation.</span></span> <span data-ttu-id="dcbdf-123">ASCII 문자 A ~ Z에 대 한 대/소문자를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbdf-123">It's only case-insensitive for the ASCII characters A through Z.</span></span>

<span data-ttu-id="dcbdf-124">다음과 같은 pragma 문을 사용 하 여 LIKE 연산자를 대/소문자를 구분 하 여 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbdf-124">You can easily make the LIKE operator case-sensitive by using the following pragma statement:</span></span>

```sql
PRAGMA case_sensitive_like = 0
```

<span data-ttu-id="dcbdf-125">LIKE 연산자의 구현을 재정의 하는 방법에 대 한 자세한 내용은 [사용자 정의 함수](user-defined-functions.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dcbdf-125">See [User-defined functions](user-defined-functions.md) for details on overriding the implementation of the LIKE operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="dcbdf-126">참조</span><span class="sxs-lookup"><span data-stu-id="dcbdf-126">See also</span></span>

* [<span data-ttu-id="dcbdf-127">사용자 정의 함수</span><span class="sxs-lookup"><span data-stu-id="dcbdf-127">User-defined functions</span></span>](user-defined-functions.md)
* [<span data-ttu-id="dcbdf-128">SQL 구문</span><span class="sxs-lookup"><span data-stu-id="dcbdf-128">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
