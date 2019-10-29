---
title: COLLECTION(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: 5a1af1aab8a084b19e48fbdbb159d7ddd8a8dd7c
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039904"
---
# <a name="collection-entity-sql"></a><span data-ttu-id="8b93c-102">COLLECTION(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8b93c-102">COLLECTION (Entity SQL)</span></span>
<span data-ttu-id="8b93c-103">COLLECTION 키워드는 인라인 함수의 정의에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b93c-103">The COLLECTION keyword is only used in the definition of an inline function.</span></span> <span data-ttu-id="8b93c-104">컬렉션 함수는 값 컬렉션에 대해 작업을 수행하고 스칼라 출력을 생성하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="8b93c-104">Collection functions are functions that operate on a collection of values and produce a scalar output.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b93c-105">구문</span><span class="sxs-lookup"><span data-stu-id="8b93c-105">Syntax</span></span>  
  
```csharp  
COLLECTION(type_definition)
```  
  
## <a name="arguments"></a><span data-ttu-id="8b93c-106">인수</span><span class="sxs-lookup"><span data-stu-id="8b93c-106">Arguments</span></span>  
 `type_definition`  
 <span data-ttu-id="8b93c-107">지원되는 형식, 행 또는 참조 컬렉션을 반환하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8b93c-107">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b93c-108">주의</span><span class="sxs-lookup"><span data-stu-id="8b93c-108">Remarks</span></span>  
 <span data-ttu-id="8b93c-109">COLLECTION 키워드에 대한 자세한 내용은 [Type Definitions](type-definitions-entity-sql.md)항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b93c-109">For more information about the COLLECTION keyword, see [Type Definitions](type-definitions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b93c-110">예제</span><span class="sxs-lookup"><span data-stu-id="8b93c-110">Example</span></span>  
 <span data-ttu-id="8b93c-111">다음 샘플에서는 COLLECTION 키워드를 사용하여 10진수 컬렉션을 인라인 쿼리 함수의 인수로 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8b93c-111">The following sample shows how to use the COLLECTION keyword to declare a collection of decimals as an argument for an inline query function.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a><span data-ttu-id="8b93c-112">참조</span><span class="sxs-lookup"><span data-stu-id="8b93c-112">See also</span></span>

- [<span data-ttu-id="8b93c-113">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="8b93c-113">Entity SQL Reference</span></span>](entity-sql-reference.md)
