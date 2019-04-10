---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 92be418e38039757437e6e673f39a7baef011528
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221784"
---
# <a name="linq-to-dataset"></a>LINQ to DataSet
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 사용 하면 쉽고 빠르게 쿼리할에 캐시 된 데이터는 <xref:System.Data.DataSet> 개체입니다. 특히, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]을 사용하면 별도의 쿼리 언어를 사용하는 대신 프로그래밍 언어 자체에서 쿼리를 작성할 수 있으므로 간편하게 쿼리할 수 있습니다. 지금 활용할 수 컴파일 타임 구문 검사, 정적 입력 및 IntelliSense 지원을 해당 쿼리에 Visual Studio에서 제공 하는 Visual Studio 개발자에 게 특히 유용 합니다.  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 사용할 수도 있습니다 하나 이상의 데이터 원본에서 통합 된 데이터에 대해 쿼리 합니다. 이 기능은 논리적으로 집계된 데이터 쿼리, 웹 응용 프로그램의 중간 계층 캐시 등과 같이 유연하게 데이터를 표현하고 처리해야 하는 여러 시나리오에 사용될 수 있습니다. 이러한 조작 방법은 일반적인 보고, 분석 및 비즈니스 인텔리전스 응용 프로그램에 특히 필요합니다.  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 기능은 주로의 확장 메서드를 통해 노출 되는 <xref:System.Data.DataRowExtensions> 및 <xref:System.Data.DataTableExtensions> 클래스. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 기반으로 하며, 기존 사용 [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] 아키텍처를 대체 하기 위한 것 및 [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] 응용 프로그램 코드에서. 기존 ADO.NET 2.0 코드는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 응용 프로그램에서 계속 사용됩니다. 다음 다이어그램에서는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]에 대한 [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)]과 데이터 저장소의 관계를 보여 줍니다.  
  
 ![LINQ to DataSet은 ADO.NET 공급자를 기반으로 한다는 보여 주는 다이어그램입니다.](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a>섹션 내용  
 [시작](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [프로그래밍 가이드](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a>참조  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a>참고자료

- [언어 통합 쿼리 (LINQ)C#](../../../csharp/programming-guide/concepts/linq/index.md)
- [언어 통합 쿼리 (LINQ)-Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [LINQ 및 ADO.NET](../../../../docs/framework/data/adonet/linq-and-ado-net.md)
- [ADO.NET](../../../../docs/framework/data/adonet/index.md)
