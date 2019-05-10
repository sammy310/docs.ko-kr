---
title: 클래스 생성자에 클래스의 기본 인스턴스를 사용하면 무한 재귀 호출이 발생할 수 있습니다.
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: 1cad1e3cf3943e945d519aee061a877c91684b4a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623478"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a><span data-ttu-id="3a93c-102">클래스 생성자에 클래스의 기본 인스턴스를 사용하면 무한 재귀 호출이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a93c-102">Use of Default Instance of a class in the class constructor could lead to infinite recursive call</span></span>
<span data-ttu-id="3a93c-103">클래스의 기본 인스턴스가 클래스의 생성자에서 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3a93c-103">A default instance of a class has been used in the constructor of the class.</span></span> <span data-ttu-id="3a93c-104">이로 인해 무한 루프라고도 하는 무한 재귀 호출이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a93c-104">This can lead to an infinite recursive call, also known as an infinite loop.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3a93c-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="3a93c-105">To correct this error</span></span>  
  
- <span data-ttu-id="3a93c-106">클래스 생성자에서 기본 인스턴스를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3a93c-106">Remove the default instance from the class constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a93c-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="3a93c-107">See also</span></span>

- [<span data-ttu-id="3a93c-108">생성자</span><span class="sxs-lookup"><span data-stu-id="3a93c-108">Constructors</span></span>](~/docs/visual-basic/programming-guide/concepts/object-oriented-programming.md#constructors)
