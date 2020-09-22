---
title: "'<typename>'은(는) 대리자 형식입니다."
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 4cc0a1221dcf65aa2a16fd7d82568c8544f27fdb
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875080"
---
# <a name="typename-is-a-delegate-type"></a><span data-ttu-id="b9c15-102">'\<typename>'은(는) 대리자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-102">'\<typename>' is a delegate type</span></span>

<span data-ttu-id="b9c15-103">' \<typename> '은 (는) 대리자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="b9c15-104">대리자 생성은 단일 AddressOf 식만 인수 목록으로 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="b9c15-105">일반적으로 대리자 생성 대신 AddressOf 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="b9c15-106">`New`대리자 클래스의 인스턴스를 만드는 절은 대리자 생성자에 잘못 된 인수 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="b9c15-107">`AddressOf`새 대리자 인스턴스를 만들 때 단일 식만 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="b9c15-108">이 오류는 대리자 생성자에 인수를 전달 하지 않거나 둘 이상의 인수를 전달 하거나 유효한 식이 아닌 단일 인수를 전달 하는 경우에 발생할 수 있습니다 `AddressOf` .</span><span class="sxs-lookup"><span data-stu-id="b9c15-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="b9c15-109">**오류 ID:** BC32008</span><span class="sxs-lookup"><span data-stu-id="b9c15-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b9c15-110">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="b9c15-110">To correct this error</span></span>  
  
- <span data-ttu-id="b9c15-111">`AddressOf`절에서 대리자 클래스의 인수 목록에 있는 단일 식을 사용 `New` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9c15-112">참조</span><span class="sxs-lookup"><span data-stu-id="b9c15-112">See also</span></span>

- [<span data-ttu-id="b9c15-113">새 운영자</span><span class="sxs-lookup"><span data-stu-id="b9c15-113">New Operator</span></span>](../operators/new-operator.md)
- [<span data-ttu-id="b9c15-114">AddressOf 연산자</span><span class="sxs-lookup"><span data-stu-id="b9c15-114">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="b9c15-115">대리자</span><span class="sxs-lookup"><span data-stu-id="b9c15-115">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="b9c15-116">방법: 대리자 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="b9c15-116">How to: Invoke a Delegate Method</span></span>](../../programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
