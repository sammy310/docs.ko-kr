---
title: Narrowing
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: 77515357ac9dc972992df09c471695aad13985c4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867930"
---
# <a name="narrowing-visual-basic"></a><span data-ttu-id="ee269-102">Narrowing(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee269-102">Narrowing (Visual Basic)</span></span>

<span data-ttu-id="ee269-103">변환 연산자 ( `CType` )가 클래스 또는 구조체를 원래 클래스 또는 구조체의 가능한 값 중 일부를 보유할 수 없는 형식으로 변환 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ee269-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that might not be able to hold some of the possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-narrowing-keyword"></a><span data-ttu-id="ee269-104">축소 키워드를 사용 하 여 변환</span><span class="sxs-lookup"><span data-stu-id="ee269-104">Converting with the Narrowing Keyword</span></span>  

 <span data-ttu-id="ee269-105">변환 프로시저는 `Public Shared` 와 함께를 지정 해야 합니다 `Narrowing` .</span><span class="sxs-lookup"><span data-stu-id="ee269-105">The conversion procedure must specify `Public Shared` in addition to `Narrowing`.</span></span>  
  
 <span data-ttu-id="ee269-106">축소 변환은 런타임에 항상 성공 하지 않으며 데이터 손실이 발생 하거나 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee269-106">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="ee269-107">예를 들어,에 대 한 `Long` `Integer` `String` `Date` 기본 형식과 파생 형식에 대 한 기본 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee269-107">Examples are `Long` to `Integer`, `String` to `Date`, and a base type to a derived type.</span></span> <span data-ttu-id="ee269-108">기본 형식에 파생 형식의 멤버가 모두 포함 되어 있지 않아 파생 형식의 인스턴스가 아닌 경우 마지막 변환은 축소입니다.</span><span class="sxs-lookup"><span data-stu-id="ee269-108">This last conversion is narrowing because the base type might not contain all the members of the derived type and thus is not an instance of the derived type.</span></span>  
  
 <span data-ttu-id="ee269-109">`Option Strict`가 이면 `On` 소비 하는 코드에서 `CType` 모든 축소 변환에를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee269-109">If `Option Strict` is `On`, the consuming code must use `CType` for all narrowing conversions.</span></span>  
  
 <span data-ttu-id="ee269-110">`Narrowing`키워드는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee269-110">The `Narrowing` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="ee269-111">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="ee269-111">Operator Statement</span></span>](../statements/operator-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="ee269-112">참조</span><span class="sxs-lookup"><span data-stu-id="ee269-112">See also</span></span>

- [<span data-ttu-id="ee269-113">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="ee269-113">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="ee269-114">Widening</span><span class="sxs-lookup"><span data-stu-id="ee269-114">Widening</span></span>](widening.md)
- [<span data-ttu-id="ee269-115">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="ee269-115">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="ee269-116">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="ee269-116">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="ee269-117">CType Function</span><span class="sxs-lookup"><span data-stu-id="ee269-117">CType Function</span></span>](../functions/ctype-function.md)
- [<span data-ttu-id="ee269-118">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="ee269-118">Option Strict Statement</span></span>](../statements/option-strict-statement.md)
