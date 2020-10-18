---
title: "'<structurename>' 구조체에는 'Custom'으로 표시되지 않은 적어도 하나의 인스턴스 멤버 변수 또는 이벤트 선언이 있어야 합니다."
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 4e7ef82659c43be08ee444eaf3f4df663f7aaa53
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159653"
---
# <a name="bc30941-structure-structurename-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-custom"></a><span data-ttu-id="deca6-102">BC30941: Structure ' \<structurename> '에는 적어도 하나의 인스턴스 멤버 변수 또는 ' Custom '으로 표시 되지 않은 인스턴스 이벤트 선언이 하나 이상 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="deca6-102">BC30941: Structure '\<structurename>' must contain at least one instance member variable or at least one instance event declaration not marked 'Custom'</span></span>

<span data-ttu-id="deca6-103">구조체 정의에는 비공유 변수 또는 비공유 noncustom 이벤트가 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="deca6-103">A structure definition does not include any nonshared variables or nonshared noncustom events.</span></span>

 <span data-ttu-id="deca6-104">모든 구조에는 모든 인스턴스가 통칭 ([공유](../modifiers/shared.md)) 하는 대신 각 특정 인스턴스 (비공유)에 적용 되는 변수 또는 이벤트가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="deca6-104">Every structure must have either a variable or an event that applies to each specific instance (nonshared) instead of to all instances collectively ([Shared](../modifiers/shared.md)).</span></span> <span data-ttu-id="deca6-105">비공유 상수, 속성 및 프로시저는이 요구 사항을 충족 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="deca6-105">Nonshared constants, properties, and procedures do not satisfy this requirement.</span></span> <span data-ttu-id="deca6-106">또한 비공유 변수가 없고 비공유 이벤트가 하나만 있는 경우 해당 이벤트는 이벤트 일 수 없습니다 `Custom` .</span><span class="sxs-lookup"><span data-stu-id="deca6-106">In addition, if there are no nonshared variables and only one nonshared event, that event cannot be a `Custom` event.</span></span>

 <span data-ttu-id="deca6-107">**오류 ID:** BC30941</span><span class="sxs-lookup"><span data-stu-id="deca6-107">**Error ID:** BC30941</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="deca6-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="deca6-108">To correct this error</span></span>

- <span data-ttu-id="deca6-109">이 아닌 변수나 이벤트를 하나 이상 정의 `Shared` 합니다.</span><span class="sxs-lookup"><span data-stu-id="deca6-109">Define at least one variable or event that is not `Shared`.</span></span> <span data-ttu-id="deca6-110">이벤트를 하나만 정의 하는 경우 noncustom 뿐 아니라 비공유 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="deca6-110">If you define only one event, it must be noncustom as well as nonshared.</span></span>

## <a name="see-also"></a><span data-ttu-id="deca6-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="deca6-111">See also</span></span>

- [<span data-ttu-id="deca6-112">구조체</span><span class="sxs-lookup"><span data-stu-id="deca6-112">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="deca6-113">방법: 구조 선언</span><span class="sxs-lookup"><span data-stu-id="deca6-113">How to: Declare a Structure</span></span>](../../programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="deca6-114">Structure 문</span><span class="sxs-lookup"><span data-stu-id="deca6-114">Structure Statement</span></span>](../statements/structure-statement.md)
