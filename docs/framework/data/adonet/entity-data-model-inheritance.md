---
title: '엔터티 데이터 모델: 상속'
ms.date: 03/30/2017
ms.assetid: 42c7ef24-710a-4af9-8493-cd41c399ecb0
ms.openlocfilehash: 4c4abc371000006d40ede3d904b0437f3f85e3e7
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738458"
---
# <a name="entity-data-model-inheritance"></a><span data-ttu-id="3a193-102">엔터티 데이터 모델: 상속</span><span class="sxs-lookup"><span data-stu-id="3a193-102">Entity Data Model: Inheritance</span></span>
<span data-ttu-id="3a193-103">EDM (엔터티 데이터 모델)은 [엔터티 형식](entity-type.md)에 대 한 상속을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a193-103">The Entity Data Model (EDM) supports inheritance for [entity types](entity-type.md).</span></span> <span data-ttu-id="3a193-104">EDM의 상속은 개체 지향 프로그래밍 언어의 클래스에 대한 상속과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="3a193-104">Inheritance in the EDM is similar to inheritance for classes in object-oriented programming languages.</span></span> <span data-ttu-id="3a193-105">개체 지향 언어의 클래스와 마찬가지로 개념적 모델에서는 다른 엔터티 형식 ( *기본 형식*)에서 상속 되는 엔터티 형식 ( *파생 된 형식*)을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a193-105">Like with classes in object-oriented languages, in a conceptual model you can define an entity type (a *derived type*) that inherits from another entity type (the *base type*).</span></span> <span data-ttu-id="3a193-106">그러나 개체 지향 프로그래밍의 클래스와는 달리, 파생 형식은 항상 기본 형식의 모든 [속성](property.md) 및 [탐색 속성](navigation-property.md) 을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a193-106">However, unlike classes in object-oriented programming, in a conceptual model the derived type always inherits all the [properties](property.md) and [navigation properties](navigation-property.md) of the base type.</span></span> <span data-ttu-id="3a193-107">파생 형식에서 상속된 속성을 재정의할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a193-107">You cannot override inherited properties in a derived type.</span></span>  
  
 <span data-ttu-id="3a193-108">개념적 모델에서는 파생 형식이 다른 파생 형식으로부터 상속받는 상속 계층 구조를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a193-108">In a conceptual model you can build inheritance hierarchies in which a derived type inherits from another derived type.</span></span> <span data-ttu-id="3a193-109">계층 구조의 맨 위에 있는 형식 (파생 형식이 아닌 계층 구조에서 한 형식)을 *루트 형식*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a193-109">The type at the top of the hierarchy (the one type in the hierarchy that is not a derived type) is called the *root type*.</span></span> <span data-ttu-id="3a193-110">상속 계층 구조에서 루트 형식에 [엔터티 키](entity-key.md) 를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a193-110">In an inheritance hierarchy, the [entity key](entity-key.md) must be defined on the root type.</span></span>  
  
 <span data-ttu-id="3a193-111">파생 형식이 둘 이상의 형식으로부터 상속받는 상속 계층 구조는 작성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a193-111">You cannot build inheritance hierarchies in which a derived type inherits from more than one type.</span></span> <span data-ttu-id="3a193-112">예를 들어, `Book` 엔터티 형식이 포함된 개념적 모델에서는 각각 `FictionBook`으로부터 상속되는 파생 형식 `NonFictionBook`과 `Book`을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a193-112">For example, in a conceptual model with a `Book` entity type, you could define derived types `FictionBook` and `NonFictionBook` that each inherit from `Book`.</span></span> <span data-ttu-id="3a193-113">그러나 `FictionBook` 및 `NonFictionBook` 형식에서 모두 상속되는 형식을 정의할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a193-113">However, you could not then define a type that inherits from both the `FictionBook` and `NonFictionBook` types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a193-114">예제</span><span class="sxs-lookup"><span data-stu-id="3a193-114">Example</span></span>  

<span data-ttu-id="3a193-115">다음 다이어그램에서는 `Book`, `FictionBook`, `Publisher`및 `Author`의 네 가지 엔터티 형식이 포함 된 개념적 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a193-115">The following diagram shows a conceptual model with four entity types: `Book`, `FictionBook`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="3a193-116">`FictionBook` 엔터티 형식은 `Book` 엔터티 형식에서 상속되는 파생 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3a193-116">The `FictionBook` entity type is a derived type, inheriting from the `Book` entity type.</span></span> <span data-ttu-id="3a193-117">`FictionBook` 형식은 `ISBN (Key)`, `Title` 및 `Revision` 속성을 상속하고 `Genre`라는 추가 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3a193-117">The `FictionBook` type inherits the `ISBN (Key)`, `Title`, and `Revision` properties, and defines an additional property called `Genre`.</span></span>  
  
 ![네 개의 엔터티 형식이 포함 된 개념적 모델을 보여 주는 다이어그램입니다.](./media/entity-data-model-inheritance/entity-type-inheritance.gif)  
  
 <span data-ttu-id="3a193-119">[ADO.NET Entity Framework](./ef/index.md) 에서는[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)(개념 스키마 정의 언어) 이라는 DSL (도메인별 언어)을 사용 하 여 개념적 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a193-119">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="3a193-120">다음 CSDL에서는 위의 다이어그램에 표시된 `FictionBook` 형식에서 상속되는 엔터티 형식 `Book`을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3a193-120">The following CSDL defines an entity type, `FictionBook`, that inherits from the `Book` type (as in the diagram above):</span></span>  
  
 [!code-xml[EDM_Example_Model#DerivedType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books5.edmx#derivedtype)]  
  
## <a name="see-also"></a><span data-ttu-id="3a193-121">참조</span><span class="sxs-lookup"><span data-stu-id="3a193-121">See also</span></span>

- [<span data-ttu-id="3a193-122">엔터티 데이터 모델의 주요 개념</span><span class="sxs-lookup"><span data-stu-id="3a193-122">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="3a193-123">엔터티 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="3a193-123">Entity Data Model</span></span>](entity-data-model.md)
