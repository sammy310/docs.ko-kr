---
title: '방법: EntityConnection 연결 문자열 빌드'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5bd1a748-3df7-4d0a-a607-14f25e3175e9
ms.openlocfilehash: f0918950921e620f724fedd8be027ffe0e2d3fa6
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854666"
---
# <a name="how-to-build-an-entityconnection-connection-string"></a><span data-ttu-id="70a14-102">방법: EntityConnection 연결 문자열 빌드</span><span class="sxs-lookup"><span data-stu-id="70a14-102">How to: Build an EntityConnection Connection String</span></span>
<span data-ttu-id="70a14-103">이 항목에서는 <xref:System.Data.EntityClient.EntityConnection>을 작성하는 방법에 대한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="70a14-103">This topic provides an example of how to build an <xref:System.Data.EntityClient.EntityConnection>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="70a14-104">이 예제의 코드를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="70a14-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="70a14-105">프로젝트에 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 을 추가 하 고 Entity Framework를 사용 하도록 프로젝트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="70a14-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="70a14-106">자세한 내용은 [방법: 엔터티 데이터 모델 마법사](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70a14-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="70a14-107">애플리케이션의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="70a14-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="70a14-108">예제</span><span class="sxs-lookup"><span data-stu-id="70a14-108">Example</span></span>  
 <span data-ttu-id="70a14-109">다음 예제에서는 기본 공급자에 대한 <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType>를 초기화한 다음 <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType> 개체를 초기화하고 이 개체를 <xref:System.Data.EntityClient.EntityConnection>의 생성자에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="70a14-109">The following example initializes the <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType> for the underlying provider, then initializes the <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType> object and passes this object to the constructor of the <xref:System.Data.EntityClient.EntityConnection>.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#buildingconnectionstringwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#buildingconnectionstringwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="70a14-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="70a14-110">See also</span></span>

- <span data-ttu-id="70a14-111">[방법: 개체 컨텍스트에서 EntityConnection 사용](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738461(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="70a14-111">[How to: Use EntityConnection with an Object Context](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738461(v=vs.100))</span></span>
- [<span data-ttu-id="70a14-112">Entity Framework용 EntityClient 공급자</span><span class="sxs-lookup"><span data-stu-id="70a14-112">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
