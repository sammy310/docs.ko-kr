---
title: 레코드 식 복사 및 업데이트
description: 작성을 '복사 및 업데이트 레코드 expression' 복사는 기존 레코드를 업데이트 하는 필드 지정 및 업데이트 된 레코드를 반환 하는 방법에 알아봅니다.
author: ChrSteinert
ms.date: 06/04/2016
ms.openlocfilehash: 5f9b13ebf6c456aff73872b7522d7670c068dd88
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766053"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="be52f-103">레코드 식 복사 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="be52f-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="be52f-104">A *복사 및 업데이트 레코드 식* 은 기존 레코드를 복사 하 고, 지정 된 필드를 업데이트, 업데이트 된 레코드를 반환 하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="be52f-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="be52f-105">구문</span><span class="sxs-lookup"><span data-stu-id="be52f-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a><span data-ttu-id="be52f-106">설명</span><span class="sxs-lookup"><span data-stu-id="be52f-106">Remarks</span></span>

<span data-ttu-id="be52f-107">이 가능 기존 레코드는 업데이트 되지에 레코드는 기본적으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be52f-107">Records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="be52f-108">업데이트 된 레코드는 레코드의 모든 필드를 만들려면 해야 다시 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be52f-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="be52f-109">이 작업을 간소화 하는 *복사 및 업데이트 레코드 식* 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be52f-109">To simplify this task a *copy and update record expression* can be used.</span></span> <span data-ttu-id="be52f-110">이 식은 기존 레코드를 사용, 식에서 지정 된 필드와 식으로 지정 된 누락 된 필드를 사용 하 여 동일한 유형의 새 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="be52f-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>
<span data-ttu-id="be52f-111">기존 레코드를 복사 하 고 필드 값의 일부 변경 해야 할 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be52f-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="be52f-112">사용 예를 들어 새로 만든된 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="be52f-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="be52f-113">사용 하 여 해당 레코드의 필드에만 업데이트 하는 경우는 *복사 및 업데이트 레코드 식* 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="be52f-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="be52f-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="be52f-114">See also</span></span>

- [<span data-ttu-id="be52f-115">레코드</span><span class="sxs-lookup"><span data-stu-id="be52f-115">Records</span></span>](records.md)
- [<span data-ttu-id="be52f-116">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="be52f-116">F# Language Reference</span></span>](index.md)