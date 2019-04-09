---
title: 입력 문자 집합(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 13d291d3-e6bc-4719-b953-758b61a590b6
ms.openlocfilehash: 3795660cf6086aa67596f31e49c4d950aa653d86
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109729"
---
# <a name="input-character-set-entity-sql"></a><span data-ttu-id="9eb17-102">입력 문자 집합(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9eb17-102">Input Character Set (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="9eb17-103">u t F-16에서으로 인코딩된 UNICODE 문자를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9eb17-103">accepts UNICODE characters encoded in UTF-16.</span></span>  
  
 <span data-ttu-id="9eb17-104">문자열 리터럴은 작은따옴표로 묶인 임의의 UTF-16 문자(예:</span><span class="sxs-lookup"><span data-stu-id="9eb17-104">String literals can contain any UTF-16 character enclosed in single quotes.</span></span> <span data-ttu-id="9eb17-105">N'文字列リテラル')를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eb17-105">For example, N'文字列リテラル'.</span></span> <span data-ttu-id="9eb17-106">문자열 리터럴을 비교할 때 원래 UTF-16 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9eb17-106">When string literals are compared, the original UTF-16 values are used.</span></span> <span data-ttu-id="9eb17-107">예를 들어, N'ABC'는 일본어와 라틴어에서 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9eb17-107">For example, N'ABC' is different in Japanese and Latin codepages.</span></span>  
  
 <span data-ttu-id="9eb17-108">주석은 모든 UTF-16 문자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eb17-108">Comments can contain any UTF-16 character.</span></span>  
  
 <span data-ttu-id="9eb17-109">이스케이프 식별자는 대괄호 문자로 묶인 UTF-16 문자일 수 있습니다(예:</span><span class="sxs-lookup"><span data-stu-id="9eb17-109">Escaped identifiers can contain any UTF-16 character enclosed in square brackets.</span></span> <span data-ttu-id="9eb17-110">[エスケープされた識別子])를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eb17-110">For example, [エスケープされた識別子].</span></span> <span data-ttu-id="9eb17-111">이스케이프된 UTF-16 식별자를 비교할 때 대/소문자는 구분되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9eb17-111">The comparison of UTF-16 escaped identifiers is case insensitive.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="9eb17-112">동일 하 게 표시 되지만 다른 문자로 서로 다른 코드 페이지 문자 버전을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="9eb17-112">treats versions of letters that appear the same but are from different code pages as different characters.</span></span> <span data-ttu-id="9eb17-113">예를 들어, 해당 문자가 동일한 코드 페이지에서 제공된 경우 [ABC]는 [abc]와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9eb17-113">For example, [ABC] is equivalent to [abc] if the corresponding characters are from the same code page.</span></span> <span data-ttu-id="9eb17-114">그러나 동일한 두 식별자가 서로 다른 코드 페이지에서 제공된 경우 두 식별자는 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9eb17-114">However, if the same two identifiers are from different code pages, they are not equivalent.</span></span>  
  
 <span data-ttu-id="9eb17-115">공백은 UTF-16 공백 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="9eb17-115">White space is any UTF-16 white space character.</span></span>  
  
 <span data-ttu-id="9eb17-116">줄 바꿈은 표준화된 UTF-16 줄 바꿈 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="9eb17-116">A newline is any normalized UTF-16 newline character.</span></span> <span data-ttu-id="9eb17-117">예를 들어, '\n' 및 '\r\n'은 줄 바꿈 문자로 인식되지만 '\r'은 줄 바꿈 문자가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9eb17-117">For example, '\n' and '\r\n' are considered newline characters, but '\r' is not a newline character.</span></span>  
  
 <span data-ttu-id="9eb17-118">키워드, 식 및 문장 부호는 라틴어로 표준화된 UTF-16 문자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eb17-118">Keywords, expressions, and punctuation can be any UTF-16 character that normalizes to Latin.</span></span> <span data-ttu-id="9eb17-119">예를 들어, 일본어 코드 페이지에서 SELECT는 유효한 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="9eb17-119">For example, SELECT in a Japanese codepage is a valid keyword.</span></span>  
  
 <span data-ttu-id="9eb17-120">키워드, 식 및 문장 부호는 라틴 문자일 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eb17-120">Keywords, expressions, and punctuation can only be Latin characters.</span></span> `SELECT` <span data-ttu-id="9eb17-121">일본어 코드 페이지에는 키워드가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9eb17-121">in a Japanese codepage is not a keyword.</span></span> <span data-ttu-id="9eb17-122">+,-, \*, /, =, (,), ', [,] 및 여기에서 언급 되지 않은 기타 언어 구문은 라틴 문자만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="9eb17-122">+, -, \*, /, =, (, ), ‘, [, ] and any other language construct not quoted here can only be Latin characters.</span></span>  
  
 <span data-ttu-id="9eb17-123">단일 식별자는 라틴 문자만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="9eb17-123">Simple identifiers can only be Latin characters.</span></span> <span data-ttu-id="9eb17-124">이렇게 하면 원래 값만 비교되므로 비교하는 동안 모호성을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eb17-124">This avoids ambiguity during comparison, because original values are compared.</span></span> <span data-ttu-id="9eb17-125">예를 들어, ABC는 일본어와 라틴어에서에서 다른 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9eb17-125">For example, ABC would be different in Japanese and Latin codepages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eb17-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="9eb17-126">See also</span></span>

- [<span data-ttu-id="9eb17-127">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="9eb17-127">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
