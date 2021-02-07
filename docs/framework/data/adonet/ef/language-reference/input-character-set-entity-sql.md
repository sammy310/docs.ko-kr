---
description: '자세한 정보: 입력 문자 집합 (Entity SQL)'
title: 입력 문자 집합(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 13d291d3-e6bc-4719-b953-758b61a590b6
ms.openlocfilehash: b17b9b2022a49717aace3c9f642ac62a2f30b2b5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748526"
---
# <a name="input-character-set-entity-sql"></a><span data-ttu-id="bcce2-103">입력 문자 집합(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="bcce2-103">Input Character Set (Entity SQL)</span></span>

[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="bcce2-104">에서는 UTF-16으로 인코딩된 UNICODE 문자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bcce2-104">accepts UNICODE characters encoded in UTF-16.</span></span>  
  
 <span data-ttu-id="bcce2-105">문자열 리터럴은 작은따옴표로 묶인 임의의 UTF-16 문자(예:</span><span class="sxs-lookup"><span data-stu-id="bcce2-105">String literals can contain any UTF-16 character enclosed in single quotes.</span></span> <span data-ttu-id="bcce2-106">N'文字列リテラル')를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcce2-106">For example, N'文字列リテラル'.</span></span> <span data-ttu-id="bcce2-107">문자열 리터럴을 비교할 때 원래 UTF-16 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcce2-107">When string literals are compared, the original UTF-16 values are used.</span></span> <span data-ttu-id="bcce2-108">예를 들어, N'ABC'는 일본어와 라틴어에서 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="bcce2-108">For example, N'ABC' is different in Japanese and Latin codepages.</span></span>  
  
 <span data-ttu-id="bcce2-109">주석은 모든 UTF-16 문자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcce2-109">Comments can contain any UTF-16 character.</span></span>  
  
 <span data-ttu-id="bcce2-110">이스케이프 식별자는 대괄호 문자로 묶인 UTF-16 문자일 수 있습니다(예:</span><span class="sxs-lookup"><span data-stu-id="bcce2-110">Escaped identifiers can contain any UTF-16 character enclosed in square brackets.</span></span> <span data-ttu-id="bcce2-111">[エスケープされた識別子])를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcce2-111">For example, [エスケープされた識別子].</span></span> <span data-ttu-id="bcce2-112">이스케이프된 UTF-16 식별자를 비교할 때 대/소문자는 구분되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bcce2-112">The comparison of UTF-16 escaped identifiers is case insensitive.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="bcce2-113">에서는 나타나는 모양은 같지만 서로 다른 코드 페이지에서 가져온 문자 버전을 다른 문자로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="bcce2-113">treats versions of letters that appear the same but are from different code pages as different characters.</span></span> <span data-ttu-id="bcce2-114">예를 들어, 해당 문자가 동일한 코드 페이지에서 제공된 경우 [ABC]는 [abc]와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bcce2-114">For example, [ABC] is equivalent to [abc] if the corresponding characters are from the same code page.</span></span> <span data-ttu-id="bcce2-115">그러나 동일한 두 식별자가 서로 다른 코드 페이지에서 제공된 경우 두 식별자는 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bcce2-115">However, if the same two identifiers are from different code pages, they are not equivalent.</span></span>  
  
 <span data-ttu-id="bcce2-116">공백은 UTF-16 공백 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="bcce2-116">White space is any UTF-16 white space character.</span></span>  
  
 <span data-ttu-id="bcce2-117">줄 바꿈은 표준화된 UTF-16 줄 바꿈 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="bcce2-117">A newline is any normalized UTF-16 newline character.</span></span> <span data-ttu-id="bcce2-118">예를 들어, '\n' 및 '\r\n'은 줄 바꿈 문자로 인식되지만 '\r'은 줄 바꿈 문자가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="bcce2-118">For example, '\n' and '\r\n' are considered newline characters, but '\r' is not a newline character.</span></span>  
  
 <span data-ttu-id="bcce2-119">키워드, 식 및 문장 부호는 라틴어로 표준화된 UTF-16 문자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcce2-119">Keywords, expressions, and punctuation can be any UTF-16 character that normalizes to Latin.</span></span> <span data-ttu-id="bcce2-120">예를 들어, 일본어 코드 페이지에서 SELECT는 유효한 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="bcce2-120">For example, SELECT in a Japanese codepage is a valid keyword.</span></span>  
  
 <span data-ttu-id="bcce2-121">키워드, 식 및 문장 부호는 라틴 문자일 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcce2-121">Keywords, expressions, and punctuation can only be Latin characters.</span></span> <span data-ttu-id="bcce2-122">일본어 코드 페이지에서 `SELECT`는 키워드가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="bcce2-122">`SELECT` in a Japanese codepage is not a keyword.</span></span> <span data-ttu-id="bcce2-123">+,-, \* ,/, =, (,), ', [,] 및 여기에서 따옴표로 묶지 않은 다른 모든 언어 구문은 라틴어 문자만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcce2-123">+, -, \*, /, =, (, ), ‘, [, ] and any other language construct not quoted here can only be Latin characters.</span></span>  
  
 <span data-ttu-id="bcce2-124">단일 식별자는 라틴 문자만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="bcce2-124">Simple identifiers can only be Latin characters.</span></span> <span data-ttu-id="bcce2-125">이렇게 하면 원래 값만 비교되므로 비교하는 동안 모호성을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcce2-125">This avoids ambiguity during comparison, because original values are compared.</span></span> <span data-ttu-id="bcce2-126">예를 들어, ABC는 일본어와 라틴어에서 서로 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcce2-126">For example, ABC would be different in Japanese and Latin codepages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcce2-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bcce2-127">See also</span></span>

- [<span data-ttu-id="bcce2-128">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="bcce2-128">Entity SQL Overview</span></span>](entity-sql-overview.md)
