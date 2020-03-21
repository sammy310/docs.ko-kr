---
title: '방법: LINQ를 사용하여 쿼리 결과의 최소값 또는 최대값 찾기'
ms.date: 07/20/2015
helpviewer_keywords:
- max operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- minimum values [LINQ in Visual Basic]
- min operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], minimum and maximum values
- Max property
- maximum values [LINQ in Visual Basic]
- Aggregate clause [Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 238b763b-7dcd-4b14-8050-b65500a4f71c
ms.openlocfilehash: ef5f218cdcc7275f616486110825ad0b9df11cc3
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112364"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a>방법: LINQ를 사용하여 쿼리 결과의 최소값 또는 최대값 찾기(Visual Basic)
LINQ(언어 통합 쿼리)를 사용하면 데이터베이스 정보에 쉽게 액세스하고 쿼리를 실행할 수 있습니다.  
  
 다음 예제에서는 SQL Server 데이터베이스에 대해 쿼리를 수행하는 새 응용 프로그램을 만드는 방법을 보여 주습니다. 샘플은 `Aggregate` 및 `Group By` 절을 사용하여 결과에 대한 최소값과 최대값을 결정합니다. 자세한 내용은 집계 절 및 [그룹별](../../../../visual-basic/language-reference/queries/group-by-clause.md) [절을](../../../../visual-basic/language-reference/queries/aggregate-clause.md) 참조하십시오.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용합니다. 이 데이터베이스가 개발 컴퓨터에 없는 경우 Microsoft 다운로드 센터에서 다운로드할 수 있습니다. 지침은 샘플 [데이터베이스 다운로드를](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)참조하십시오.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="create-a-connection-to-a-database"></a>데이터베이스에 대한 연결 만들기  
  
1. Visual Studio에서 **보기** 메뉴에서 **서버 탐색기**/데이터베이스 탐색기를 클릭하여 **서버 탐색기**/**데이터베이스 탐색기를** 엽니다.**Database Explorer**  
  
2. **서버 탐색기**/**데이터베이스 탐색기에서** **데이터 연결을** 마우스 오른쪽 단추로 클릭한 다음 연결 **추가**를 클릭합니다.  
  
3. Northwind 샘플 데이터베이스에 대한 유효한 연결을 지정합니다.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>SQL 파일에 LINQ가 포함된 프로젝트를 추가하려면  
  
1. 비주얼 스튜디오에서 **파일** 메뉴에서 **새로** 를 가리킨 다음 **프로젝트를**클릭합니다. 시각적 기본 **Windows 양식 응용 프로그램을** 프로젝트 유형으로 선택합니다.  
  
2. **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다. LINQ에서 SQL 클래스 항목 항목 **템플릿을 선택합니다.**  
  
3. 파일 이름을 `northwind.dbml`로 지정합니다. **추가**를 클릭합니다. northwind.dbml 파일에 대해 개체 관계형 디자이너(O/R 디자이너)가 열립니다.  
  
## <a name="add-tables-to-query-to-the-or-designer"></a>O/R 디자이너에 쿼리할 테이블 추가  
  
1. **서버 탐색기**/**데이터베이스 탐색기에서**Northwind 데이터베이스에 대한 연결을 확장합니다. **테이블** 폴더를 확장합니다.  
  
     O/R 디자이너를 닫은 경우 이전에 추가한 northwind.dbml 파일을 두 번 클릭하여 다시 열 수 있습니다.  
  
2. Customers 테이블을 클릭하고 디자이너의 왼쪽 창으로 드래그합니다. Orders 테이블을 클릭하고 디자이너의 왼쪽 창으로 드래그합니다.  
  
     디자이너는 프로젝트에 `Customer` `Order` 대한 새 개체와 개체를 만듭니다. 디자이너는 테이블 간의 관계를 자동으로 감지하고 관련 개체에 대한 자식 속성을 만듭니다. 예를 들어 IntelliSense는 개체에 `Customer` 해당 `Orders` 고객과 관련된 모든 주문에 대한 속성이 있음을 표시합니다.  
  
3. 변경 내용을 저장하고 디자이너를 닫습니다.  
  
4. 프로젝트를 저장합니다.  
  
## <a name="add-code-to-query-the-database-and-display-the-results"></a>데이터베이스를 쿼리하고 결과를 표시하는 코드를 추가합니다.  
  
1. 도구 **상자에서**컨트롤을 <xref:System.Windows.Forms.DataGridView> 프로젝트의 기본 Windows 양식인 Form1로 드래그합니다.  
  
2. 양식 1을 두 번 클릭하여 `Load` 양식의 이벤트에 코드를 추가합니다.  
  
3. O/R 디자이너에 테이블을 추가하면 디자이너가 <xref:System.Data.Linq.DataContext> 프로젝트에 대한 개체를 추가했습니다. 이 개체에는 각 테이블에 대한 개별 개체 및 컬렉션 외에 해당 테이블에 액세스해야 하는 코드가 포함되어 있습니다. 프로젝트의 <xref:System.Data.Linq.DataContext> 개체는 .dbml 파일의 이름을 기반으로 이름이 지정됩니다. 이 프로젝트의 경우 <xref:System.Data.Linq.DataContext> 개체 `northwindDataContext`이름이 지정됩니다.  
  
     코드의 <xref:System.Data.Linq.DataContext> 인스턴스를 만들고 O/R 디자이너가 지정한 테이블을 쿼리할 수 있습니다.  
  
     이벤트에 다음 코드를 `Load` 추가합니다. 이 코드는 데이터 컨텍스트의 속성으로 노출되는 테이블을 쿼리하고 결과에 대한 최소값과 최대값을 결정합니다. 샘플에서는 절을 `Aggregate` 사용하여 단일 결과를 쿼리하고 `Group By` 절은 그룹화된 결과에 대한 평균을 표시합니다.  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. **F5를** 눌러 프로젝트를 실행하고 결과를 봅니다.  
  
## <a name="see-also"></a>참고 항목

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [쿼리](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [데이터 컨텍스트 메서드(O/R 디자이너)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
