---
title: '방법: LINQ를 사용하여 데이터 개수, 합 또는 평균 계산'
ms.date: 07/20/2015
helpviewer_keywords:
- average operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- queries [LINQ in Visual Basic], sum results
- Aggregate clause [Visual Basic]
- sum operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], counting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- count operator [LINQ in Visual Basic]
ms.assetid: 51ca1f59-7770-4884-8b76-113002e54fc0
ms.openlocfilehash: 8be585c3e11bc3637b2dd1cfaf3437620aa2ba09
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405019"
---
# <a name="how-to-count-sum-or-average-data-by-using-linq-visual-basic"></a>방법: LINQ를 사용하여 데이터 개수, 합 또는 평균 계산(Visual Basic)
LINQ (통합 언어 쿼리)를 사용 하면 데이터베이스 정보에 쉽게 액세스 하 고 쿼리를 실행할 수 있습니다.  
  
 다음 예에서는 SQL Server 데이터베이스에 대해 쿼리를 수행 하는 새 응용 프로그램을 만드는 방법을 보여 줍니다. 이 샘플에서는 and 절을 사용 하 여 결과의 수, 합계 및 평균을 계산 합니다 `Aggregate` `Group By` . 자세한 내용은 [Aggregate 절](../../../language-reference/queries/aggregate-clause.md) 및 [Group By 절](../../../language-reference/queries/group-by-clause.md)을 참조 하세요.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용 합니다. 이 데이터베이스가 개발 컴퓨터에 없는 경우 Microsoft 다운로드 센터에서 다운로드할 수 있습니다. 지침은 [샘플 데이터베이스 다운로드](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)를 참조 하세요.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>데이터베이스에 대 한 연결을 만들려면  
  
1. Visual Studio의 **Server Explorer** / **Database Explorer** **Server Explorer** / **보기** 메뉴에서 서버 탐색기**데이터베이스 탐색기** 를 클릭 하 여 서버 탐색기 데이터베이스 탐색기를 엽니다.  
  
2. **서버 탐색기**데이터베이스 탐색기에서 **데이터 연결** 을 마우스 오른쪽 단추로 클릭 한 / **Database Explorer** 다음 **연결 추가**를 클릭 합니다.  
  
3. Northwind 샘플 데이터베이스에 대 한 올바른 연결을 지정 하십시오.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>LINQ to SQL 파일을 포함 하는 프로젝트를 추가 하려면  
  
1. Visual Studio의 **파일** 메뉴에서 **새로 만들기** 를 가리킨 다음 **프로젝트**를 클릭 합니다. Visual Basic **Windows Forms 응용 프로그램** 을 프로젝트 형식으로 선택 합니다.  
  
2. **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다. **LINQ to SQL 클래스** 항목 템플릿을 선택 합니다.  
  
3. 파일 이름을 `northwind.dbml`로 지정합니다. **추가**를 클릭합니다. Northwind .dbml 파일에 대해 개체 관계형 디자이너 (O/R 디자이너)가 열립니다.  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>O/R 디자이너에 쿼리할 테이블을 추가 하려면  
  
1. **서버 탐색기** / **데이터베이스 탐색기**에서 Northwind 데이터베이스에 대 한 연결을 확장 합니다. **테이블** 폴더를 확장합니다.  
  
     O/R 디자이너를 닫은 경우 앞에서 추가한 각각의 .dbml 파일을 두 번 클릭 하 여 다시 열 수 있습니다.  
  
2. Customers 테이블을 클릭 하 고 디자이너의 왼쪽 창으로 끌어 놓습니다. Orders 테이블을 클릭 하 고 디자이너의 왼쪽 창으로 끌어 놓습니다.  
  
     디자이너에서 `Customer` `Order` 프로젝트에 대 한 새 및 개체를 만듭니다. 디자이너는 자동으로 테이블 간의 관계를 검색 하 고 관련 개체의 자식 속성을 만듭니다. 예를 들어 IntelliSense는 `Customer` `Orders` 해당 고객과 관련 된 모든 주문에 대 한 속성을 개체에 포함 하는 것을 보여 줍니다.  
  
3. 변경 내용을 저장 하 고 디자이너를 닫습니다.  
  
4. 프로젝트를 저장합니다.  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>데이터베이스를 쿼리하고 결과를 표시 하는 코드를 추가 하려면  
  
1. **도구 상자**에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 프로젝트의 기본 Windows 폼, Form1에 끌어 놓습니다.  
  
2. Form1을 두 번 클릭 하 여 폼의 이벤트에 코드를 추가 `Load` 합니다.  
  
3. O/R 디자이너에 테이블을 추가 하면 디자이너에서 <xref:System.Data.Linq.DataContext> 프로젝트에 대 한 개체를 추가 합니다. 이 개체에는 해당 테이블에 액세스 하 고 각 테이블에 대 한 개별 개체 및 컬렉션에 액세스 하는 데 필요한 코드가 포함 되어 있습니다. <xref:System.Data.Linq.DataContext>프로젝트에 대 한 개체는 .dbml 파일의 이름을 기반으로 이름이 지정 됩니다. 이 프로젝트의 경우 <xref:System.Data.Linq.DataContext> 개체의 이름은 `northwindDataContext` 입니다.  
  
     코드에서의 인스턴스를 만들고 <xref:System.Data.Linq.DataContext> O/R 디자이너에 지정 된 테이블을 쿼리할 수 있습니다.  
  
     이벤트에 다음 코드를 추가 `Load` 하 여의 속성으로 표시 되는 테이블을 쿼리하고 <xref:System.Data.Linq.DataContext> 결과의 개수, 합계 및 평균을 계산 합니다. 이 샘플에서는 절을 사용 하 여 단일 결과를 쿼리하고 절을 사용 하 여 `Aggregate` `Group By` 그룹화 된 결과의 평균을 표시 합니다.  
  
     [!code-vb[VbLINQToSQLHowTos#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form6.vb#13)]  
  
4. F5 키를 눌러 프로젝트를 실행 하 고 결과를 확인 합니다.  
  
## <a name="see-also"></a>참고 항목

- [LINQ](index.md)
- [쿼리](../../../language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext 메서드 (O/R 디자이너)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Aggregate Clause](../../../language-reference/queries/aggregate-clause.md)
- [Group By 절](../../../language-reference/queries/group-by-clause.md)
