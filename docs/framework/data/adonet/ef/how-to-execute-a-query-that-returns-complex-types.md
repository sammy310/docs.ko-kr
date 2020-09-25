---
title: '방법: 복합 형식을 반환하는 쿼리 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: e5358e3a1295b180356ed6c127111313b44de277
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198485"
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a><span data-ttu-id="f3264-102">방법: 복합 형식을 반환하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="f3264-102">How to: Execute a Query that Returns Complex Types</span></span>

<span data-ttu-id="f3264-103">이 항목에서는 복합 형식의 속성이 포함된 엔터티 형식 개체를 반환하는 [!INCLUDE[esql](../../../../../includes/esql-md.md)] 쿼리를 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3264-103">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that returns entity type objects that contain a property of a complex type.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="f3264-104">이 예제의 코드를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="f3264-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="f3264-105">프로젝트에 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 을 추가 하 고 Entity Framework를 사용 하도록 프로젝트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3264-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="f3264-106">자세한 내용은 [방법: 엔터티 데이터 모델 마법사 사용](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3264-106">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="f3264-107">애플리케이션의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f3264-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. <span data-ttu-id="f3264-108">.Edmx 파일을 두 번 클릭 하 여 Entity Designer의 [모델 브라우저 창](/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) 에 모델을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3264-108">Double click the .edmx file to display the model in the [Model Browser window](/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) of the Entity Designer.</span></span> <span data-ttu-id="f3264-109">Entity Designer 화면에서 `Email` `Phone` 엔터티 형식의 및 속성을 선택 하 `Contact` 고 마우스 오른쪽 단추를 클릭 한 다음 **새 복합 형식으로 리팩터링**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3264-109">On the Entity Designer surface, select the `Email` and `Phone` properties of the `Contact` entity type, then right-click and select **Refactor into New Complex Type**.</span></span>  
  
4. <span data-ttu-id="f3264-110">선택한 및 속성을 포함 하는 새 복합 형식이 `Email` `Phone` **모델 브라우저**에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3264-110">A new complex type with the selected `Email` and `Phone` properties is added to the **Model Browser**.</span></span> <span data-ttu-id="f3264-111">복합 형식에는 기본 이름이 지정 됩니다. `EmailPhone` **속성** 창에서 형식의 이름을으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f3264-111">The complex type is given a default name: rename the type to `EmailPhone` in the **Properties** window.</span></span> <span data-ttu-id="f3264-112">또한 새 `ComplexProperty` 속성이 `Contact` 엔터티 형식에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3264-112">Also, a new `ComplexProperty` property is added to the `Contact` entity type.</span></span> <span data-ttu-id="f3264-113">속성의 이름을 `EmailPhoneComplexType.`으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f3264-113">Rename the property to `EmailPhoneComplexType.`</span></span>  
  
     <span data-ttu-id="f3264-114">엔터티 데이터 모델 마법사를 사용 하 여 복합 형식을 만들고 수정 하는 방법에 대 한 자세한 내용은 [방법: 기존 속성을 복합 형식 속성으로 리팩터링](/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) 및 [방법: 복합 형식 만들기 및 수정](/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3264-114">For information about creating and modifying complex types by using the Entity Data Model Wizard, see [How to: Refactor Existing Properties into a Complex Type Property](/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) and [How to: Create and Modify Complex Types](/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3264-115">예제</span><span class="sxs-lookup"><span data-stu-id="f3264-115">Example</span></span>  

 <span data-ttu-id="f3264-116">다음 예제에서는 개체의 컬렉션을 반환 하 `Contact` 고 개체의 두 속성 `Contact` `ContactID` 및 복합 형식의 값을 표시 하는 쿼리를 실행 합니다 `EmailPhoneComplexType` .</span><span class="sxs-lookup"><span data-stu-id="f3264-116">The following example executes a query that returns a collection of `Contact` objects and displays two properties of the `Contact` objects: `ContactID` and the values of the `EmailPhoneComplexType` complex type.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
