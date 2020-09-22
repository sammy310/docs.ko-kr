---
title: "'<keyword>'은(는) 인스턴스 메서드 안에서만 사용할 수 있습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: af436b8fd57ff0d2747c766a64af175760931009
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873895"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a><span data-ttu-id="834dc-102">'\<keyword>'은(는) 인스턴스 메서드 안에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="834dc-102">'\<keyword>' is valid only within an instance method</span></span>

<span data-ttu-id="834dc-103">`Me`, `MyClass` 및 키워드는 `MyBase` 특정 클래스 인스턴스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="834dc-103">The `Me`, `MyClass`, and `MyBase` keywords refer to specific class instances.</span></span> <span data-ttu-id="834dc-104">공유 또는 프로시저 내에서는 사용할 수 `Function` 없습니다 `Sub` .</span><span class="sxs-lookup"><span data-stu-id="834dc-104">You cannot use them inside a shared `Function` or `Sub` procedure.</span></span>  
  
 <span data-ttu-id="834dc-105">**오류 ID:** BC30043</span><span class="sxs-lookup"><span data-stu-id="834dc-105">**Error ID:** BC30043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="834dc-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="834dc-106">To correct this error</span></span>  
  
- <span data-ttu-id="834dc-107">프로시저에서 키워드를 제거 하거나 `Shared` 프로시저 선언에서 키워드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="834dc-107">Remove the keyword from the procedure, or remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="834dc-108">참조</span><span class="sxs-lookup"><span data-stu-id="834dc-108">See also</span></span>

- [<span data-ttu-id="834dc-109">개체 변수 할당</span><span class="sxs-lookup"><span data-stu-id="834dc-109">Object Variable Assignment</span></span>](../../programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="834dc-110">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="834dc-110">Me, My, MyBase, and MyClass</span></span>](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="834dc-111">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="834dc-111">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
