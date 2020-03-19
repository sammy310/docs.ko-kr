---
title: 데이터 정렬
ms.date: 12/13/2019
description: 사용자 지정 정렬 시퀀스를 만드는 방법에 대해 알아봅니다.
ms.openlocfilehash: b93c82a4ace154b8293b05effa8f9e9294fa7708
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2020
ms.locfileid: "79506543"
---
# <a name="collation"></a><span data-ttu-id="24003-103">데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="24003-103">Collation</span></span>

<span data-ttu-id="24003-104">정렬 시퀀스는 텍스트 값을 비교하여 순서와 같음을 결정할 때 SQLite에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="24003-104">Collating sequences are used by SQLite when comparing TEXT values to determine order and equality.</span></span> <span data-ttu-id="24003-105">SQL 쿼리에서 열을 만들거나 작업당 작업을 수행할 때 사용할 데이터 정렬을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24003-105">You can specify which collation to use when creating columns or per-operation in SQL queries.</span></span> <span data-ttu-id="24003-106">SQLite는 기본적으로 세 개의 정렬 시퀀스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="24003-106">SQLite includes three collating sequences by default.</span></span>

| <span data-ttu-id="24003-107">데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="24003-107">Collation</span></span> | <span data-ttu-id="24003-108">Description</span><span class="sxs-lookup"><span data-stu-id="24003-108">Description</span></span>                               |
| --------- | ----------------------------------------- |
| <span data-ttu-id="24003-109">RTRIM</span><span class="sxs-lookup"><span data-stu-id="24003-109">RTRIM</span></span>     | <span data-ttu-id="24003-110">후행 공백 무시</span><span class="sxs-lookup"><span data-stu-id="24003-110">Ignores trailing whitespace</span></span>               |
| <span data-ttu-id="24003-111">없음 없음</span><span class="sxs-lookup"><span data-stu-id="24003-111">NOCASE</span></span>    | <span data-ttu-id="24003-112">ASCII 문자 A-Z에 대한 대/소문자 구분되지 않음</span><span class="sxs-lookup"><span data-stu-id="24003-112">Case-insensitive for ASCII characters A-Z</span></span> |
| <span data-ttu-id="24003-113">BINARY</span><span class="sxs-lookup"><span data-stu-id="24003-113">BINARY</span></span>    | <span data-ttu-id="24003-114">대/소문자를 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24003-114">Case-sensitive.</span></span> <span data-ttu-id="24003-115">바이트를 직접 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="24003-115">Compares bytes directly</span></span>   |

## <a name="custom-collation"></a><span data-ttu-id="24003-116">사용자 지정 데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="24003-116">Custom collation</span></span>

<span data-ttu-id="24003-117">고유한 정렬 시퀀스를 정의하거나 을 사용하여 <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>기본 제공 시퀀스를 재정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24003-117">You can also define your own collating sequences or override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span></span> <span data-ttu-id="24003-118">다음 예제에서는 유니코드 문자를 지원 하기 위해 NOCASE 데이터 정렬 재정의 를 보여 주다.</span><span class="sxs-lookup"><span data-stu-id="24003-118">The following example shows overriding the NOCASE collation to support Unicode characters.</span></span> <span data-ttu-id="24003-119">[전체 샘플 코드는](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs) GitHub에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24003-119">The [full sample code](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs) is available on GitHub.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a><span data-ttu-id="24003-120">Like 연산자</span><span class="sxs-lookup"><span data-stu-id="24003-120">Like operator</span></span>

<span data-ttu-id="24003-121">SQLite의 LIKE 연산자는 데이터 정렬을 존중하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24003-121">The LIKE operator in SQLite doesn't honor collations.</span></span> <span data-ttu-id="24003-122">기본 구현에는 NOCASE 데이터 정렬과 동일한 의미 체계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24003-122">The default implementation has the same semantics as the NOCASE collation.</span></span> <span data-ttu-id="24003-123">ASCII 문자 A부터 Z까지의 대/소문자에 대해서만 민감하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24003-123">It's only case-insensitive for the ASCII characters A through Z.</span></span>

<span data-ttu-id="24003-124">다음 pragma 문을 사용하여 LIKE 연산자 대/소문자를 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24003-124">You can easily make the LIKE operator case-sensitive by using the following pragma statement:</span></span>

```sql
PRAGMA case_sensitive_like = 1
```

<span data-ttu-id="24003-125">LIKE 연산자의 구현 재정의에 대한 자세한 내용은 [사용자 정의 함수를](user-defined-functions.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="24003-125">See [User-defined functions](user-defined-functions.md) for details on overriding the implementation of the LIKE operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="24003-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24003-126">See also</span></span>

* [<span data-ttu-id="24003-127">사용자 정의 기능</span><span class="sxs-lookup"><span data-stu-id="24003-127">User-defined functions</span></span>](user-defined-functions.md)
* [<span data-ttu-id="24003-128">SQL 구문</span><span class="sxs-lookup"><span data-stu-id="24003-128">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
