---
title: 이니셜라이저가 필요합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: 2c5a65443dc16a600e25fcf6dfd11c4597b3a086
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873946"
---
# <a name="initializer-expected"></a><span data-ttu-id="7fdea-102">이니셜라이저가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7fdea-102">Initializer expected</span></span>

<span data-ttu-id="7fdea-103">다음 예제와 같이 초기화 목록이 비어 있는 개체 이니셜라이저를 사용 하 여 클래스의 인스턴스를 선언 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7fdea-103">You have tried to declare an instance of a class by using an object initializer in which the initialization list is empty, as shown in the following example.</span></span>  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 <span data-ttu-id="7fdea-104">다음 예제와 같이 이니셜라이저 목록에서 하나 이상의 필드 또는 속성을 초기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fdea-104">At least one field or property must be initialized in the initializer list, as shown in the following example.</span></span>  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 <span data-ttu-id="7fdea-105">**오류 ID:** BC30996</span><span class="sxs-lookup"><span data-stu-id="7fdea-105">**Error ID:** BC30996</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7fdea-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="7fdea-106">To correct this error</span></span>  
  
1. <span data-ttu-id="7fdea-107">이니셜라이저에서 하나 이상의 필드 또는 속성을 초기화 하거나 개체 이니셜라이저를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7fdea-107">Initialize at least one field or property in the initializer, or do not use an object initializer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fdea-108">참조</span><span class="sxs-lookup"><span data-stu-id="7fdea-108">See also</span></span>

- [<span data-ttu-id="7fdea-109">개체 이니셜라이저: 명명된 형식 및 무명 형식</span><span class="sxs-lookup"><span data-stu-id="7fdea-109">Object Initializers: Named and Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="7fdea-110">방법: 개체 이니셜라이저를 사용하여 개체 선언</span><span class="sxs-lookup"><span data-stu-id="7fdea-110">How to: Declare an Object by Using an Object Initializer</span></span>](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
