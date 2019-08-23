---
title: Partial 메서드를 사용하여 비즈니스 논리 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
ms.openlocfilehash: e3f82c260a2cab85270a9f33a87eb9a9f04b72c7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964150"
---
# <a name="adding-business-logic-by-using-partial-methods"></a><span data-ttu-id="afbdd-102">Partial 메서드를 사용하여 비즈니스 논리 추가</span><span class="sxs-lookup"><span data-stu-id="afbdd-102">Adding Business Logic By Using Partial Methods</span></span>
<span data-ttu-id="afbdd-103">*부분 메서드*를 사용 하 C# 여 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 프로젝트에서 Visual Basic 및 생성 된 코드를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afbdd-103">You can customize Visual Basic and C# generated code in your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects by using *partial methods*.</span></span> <span data-ttu-id="afbdd-104">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 생성한 코드에는 부분 메서드의 일부로 시그니처를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="afbdd-104">The code that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates defines signatures as one part of a partial method.</span></span> <span data-ttu-id="afbdd-105">메서드를 구현하려면 사용자 고유의 부분 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="afbdd-105">If you want to implement the method, you can add your own partial method.</span></span> <span data-ttu-id="afbdd-106">사용자 고유의 구현을 추가하지 않으면 컴파일러에서는 부분 메서드 시그니처를 취소하고 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 기본 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="afbdd-106">If you do not add your own implementation, the compiler discards the partial methods signature and calls the default methods in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
> [!NOTE]
> <span data-ttu-id="afbdd-107">Visual Studio를 사용 하는 경우 개체 관계형 디자이너를 사용 하 여 엔터티 클래스에 유효성 검사 및 기타 사용자 지정 항목을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afbdd-107">If you are using Visual Studio, you can use the Object Relational Designer to add validation and other customizations to entity classes.</span></span>  
  
 <span data-ttu-id="afbdd-108">예를 들어 Northwind 샘플 데이터베이스의 `Customer` 클래스에 대한 기본 매핑에는 다음 부분 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="afbdd-108">For example, the default mapping for the `Customer` class in the Northwind sample database includes the following partial method:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 <span data-ttu-id="afbdd-109">다음과 같은 코드를 사용자 고유의 부분 `Customer` 클래스에 추가하여 사용자 고유의 메서드를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afbdd-109">You can implement your own method by adding code such as the following to your own partial `Customer` class:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 <span data-ttu-id="afbdd-110">이러한 접근 방식은 일반적으로 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 `Insert`, `Update` 및 `Delete`에 대한 기본 메서드를 재정의하고 개체 수명 주기 이벤트 동안 속성의 유효성을 검사하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="afbdd-110">This approach is typically used in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to override default methods for `Insert`, `Update`, `Delete`, and to validate properties during object life-cycle events.</span></span>  
  
 <span data-ttu-id="afbdd-111">자세한 내용은 [부분 메서드](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) 또는 [부분 (메서드) (C# 참조)](../../../../../csharp/language-reference/keywords/partial-method.md) (C#)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="afbdd-111">For more information, see [Partial Methods](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) or [partial (Method) (C# Reference)](../../../../../csharp/language-reference/keywords/partial-method.md) (C#).</span></span>  
  
## <a name="example"></a><span data-ttu-id="afbdd-112">예제</span><span class="sxs-lookup"><span data-stu-id="afbdd-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="afbdd-113">설명</span><span class="sxs-lookup"><span data-stu-id="afbdd-113">Description</span></span>  
 <span data-ttu-id="afbdd-114">다음 예제에서는 SQLMetal와 같은 코드 생성 도구에서 정의한 `ExampleClass`를 먼저 보여 준 다음 두 개의 메서드 중 하나만 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="afbdd-114">The following example shows `ExampleClass` first as it might be defined by a code-generating tool such as SQLMetal, and then how you might implement only one of the two methods.</span></span>  
  
### <a name="code"></a><span data-ttu-id="afbdd-115">코드</span><span class="sxs-lookup"><span data-stu-id="afbdd-115">Code</span></span>  
 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="afbdd-116">예제</span><span class="sxs-lookup"><span data-stu-id="afbdd-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="afbdd-117">Description</span><span class="sxs-lookup"><span data-stu-id="afbdd-117">Description</span></span>  
 <span data-ttu-id="afbdd-118">다음 예제에서는 `Shipper`와 `Order` 엔터티 간의 관계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="afbdd-118">The following example uses the relationship between `Shipper` and `Order` entities.</span></span> <span data-ttu-id="afbdd-119">메서드 중 부분 메서드는 `InsertShipper`와 `DeleteShipper`입니다.</span><span class="sxs-lookup"><span data-stu-id="afbdd-119">Note among the methods the partial methods, `InsertShipper` and `DeleteShipper`.</span></span> <span data-ttu-id="afbdd-120">이러한 메서드는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 매핑을 통해 제공된 기본 부분 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="afbdd-120">These methods override the default partial methods supplied by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mapping.</span></span>  
  
### <a name="code"></a><span data-ttu-id="afbdd-121">코드</span><span class="sxs-lookup"><span data-stu-id="afbdd-121">Code</span></span>  
 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="afbdd-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="afbdd-122">See also</span></span>

- [<span data-ttu-id="afbdd-123">데이터 변경 및 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="afbdd-123">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [<span data-ttu-id="afbdd-124">삽입, 업데이트 및 삭제 작업 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="afbdd-124">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
