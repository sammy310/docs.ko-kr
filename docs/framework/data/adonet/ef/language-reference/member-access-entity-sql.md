---
description: 에 대해 자세히 알아보세요. (멤버 액세스)(Entity SQL)
title: . (멤버 액세스)(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
ms.openlocfilehash: 94833d3525c7d17cadaef15065b3dcbdb43a6ded
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739380"
---
# <a name="-member-access-entity-sql"></a><span data-ttu-id="e708e-105">.</span><span class="sxs-lookup"><span data-stu-id="e708e-105">.</span></span> <span data-ttu-id="e708e-106">(멤버 액세스)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e708e-106">(Member Access) (Entity SQL)</span></span>

<span data-ttu-id="e708e-107">점 연산자 (.)는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 멤버 액세스 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="e708e-107">The dot operator (.) is the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] member access operator.</span></span> <span data-ttu-id="e708e-108">멤버 액세스 연산자를 사용하여 구조 개념적 모델 형식 인스턴스의 속성 또는 필드 값을 구합니다.</span><span class="sxs-lookup"><span data-stu-id="e708e-108">You use the member access operator to yield the value of a property or field of an instance of structural conceptual model type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e708e-109">구문</span><span class="sxs-lookup"><span data-stu-id="e708e-109">Syntax</span></span>  
  
```sql  
expression.identifier  
```  
  
## <a name="arguments"></a><span data-ttu-id="e708e-110">인수</span><span class="sxs-lookup"><span data-stu-id="e708e-110">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="e708e-111">구조 개념적 모델 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="e708e-111">An instance of a structural conceptual model type.</span></span>  
  
 `identifier`  
 <span data-ttu-id="e708e-112">개체 인스턴스에 속하는 속성 또는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="e708e-112">A property or field that belongs to an object instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e708e-113">설명</span><span class="sxs-lookup"><span data-stu-id="e708e-113">Remarks</span></span>  

 <span data-ttu-id="e708e-114">점 연산자(.)는 복합 형식 또는 엔터티 형식의 속성을 추출하는 것과 유사하게 레코드에서 필드를 추출하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e708e-114">The dot (.) operator may be used to extract fields from a record, similar to extracting properties of a complex or entity type.</span></span> <span data-ttu-id="e708e-115">예를 들어 Name 형식의 n이 Person 형식의 멤버이고 p가 Person 형식의 인스턴스인 경우, p.n은 Name 형식의 값을 제공하는 유효한 멤버 액세스 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e708e-115">For example, if n of type Name is a member of type Person, and p is an instance of type Person, then p.n is a legal member access expression that yields a value of type Name.</span></span>  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a><span data-ttu-id="e708e-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e708e-116">See also</span></span>

- [<span data-ttu-id="e708e-117">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="e708e-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
