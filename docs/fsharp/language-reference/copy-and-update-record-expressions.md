---
title: 레코드 식 복사 및 업데이트
description: 기존 레코드나 익명 레코드를 복사 하 고, 지정 된 필드를 업데이트 하 고, 업데이트 된 레코드나 익명 레코드를 반환 하는 ' 복사 및 업데이트 식 '을 작성 하는 방법에 대해 알아봅니다.
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: dfb20a6ff8282ae5988772cc0f0841db23aad942
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630384"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="45c60-103">레코드 식 복사 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="45c60-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="45c60-104">*복사 및 업데이트 레코드 식은* 기존 레코드를 복사 하 고, 지정 된 필드를 업데이트 하 고, 업데이트 된 레코드를 반환 하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="45c60-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="45c60-105">구문</span><span class="sxs-lookup"><span data-stu-id="45c60-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a><span data-ttu-id="45c60-106">설명</span><span class="sxs-lookup"><span data-stu-id="45c60-106">Remarks</span></span>

<span data-ttu-id="45c60-107">레코드와 익명 레코드는 기본적으로 변경할 수 없으므로 기존 레코드를 업데이트할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45c60-107">Records and anonymous records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="45c60-108">업데이트 된 레코드를 만들려면 레코드의 모든 필드를 다시 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c60-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="45c60-109">이 작업을 단순화 하기 위해 *복사 및 업데이트 식을* 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c60-109">To simplify this task a *copy and update expression* can be used.</span></span> <span data-ttu-id="45c60-110">이 식은 기존 레코드를 사용 하 여 식에서 지정 된 필드를 사용 하 고 식에 지정 된 누락 필드를 사용 하 여 동일한 형식으로 새를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45c60-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>

<span data-ttu-id="45c60-111">이는 기존 레코드를 복사 하 고 일부 필드 값을 변경 해야 하는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c60-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="45c60-112">새로 만든 레코드를 인스턴스로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c60-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="45c60-113">해당 레코드의 필드만 업데이트 하는 경우 다음과 같이 *복사 및 업데이트 레코드 식을* 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c60-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="45c60-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="45c60-114">See also</span></span>

- [<span data-ttu-id="45c60-115">레코드</span><span class="sxs-lookup"><span data-stu-id="45c60-115">Records</span></span>](records.md)
- [<span data-ttu-id="45c60-116">익명 레코드</span><span class="sxs-lookup"><span data-stu-id="45c60-116">Anonymous Records</span></span>](anonymous-records.md)
- [<span data-ttu-id="45c60-117">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="45c60-117">F# Language Reference</span></span>](index.md)
