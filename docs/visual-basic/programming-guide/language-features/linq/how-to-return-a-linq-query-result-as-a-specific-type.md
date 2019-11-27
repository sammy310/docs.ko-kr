---
title: '방법: LINQ 쿼리 결과를 특정 형식으로 반환'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
ms.openlocfilehash: 1084743b0c50d381375b76a3116ed7c9e6f9d769
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354209"
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a>방법: LINQ 쿼리 결과를 특정 형식으로 반환(Visual Basic)
LINQ (통합 언어 쿼리)를 사용 하면 데이터베이스 정보에 쉽게 액세스 하 고 쿼리를 실행할 수 있습니다. 기본적으로 LINQ 쿼리는 개체 목록을 익명 형식으로 반환 합니다. 쿼리가 `Select` 절을 사용 하 여 특정 형식의 목록을 반환 하도록 지정할 수도 있습니다.  
  
 다음 예에서는 SQL Server 데이터베이스에 대해 쿼리를 수행 하 고 결과를 특정 명명 된 형식으로 프로젝션 하는 새 응용 프로그램을 만드는 방법을 보여 줍니다. 자세한 내용은 [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) 및 [Select 절](../../../../visual-basic/language-reference/queries/select-clause.md)을 참조 하세요.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용 합니다. 이 데이터베이스가 개발 컴퓨터에 없는 경우 Microsoft 다운로드 센터에서 다운로드할 수 있습니다. 지침은 [샘플 데이터베이스 다운로드](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)를 참조 하세요.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>데이터베이스에 대 한 연결을 만들려면  
  
1. Visual Studio의 **보기** 메뉴에서 **서버 탐색기**/**데이터베이스 탐색기** 를 클릭 하 여 **서버 탐색기**/**데이터베이스 탐색기** 를 엽니다.  
  
2. **서버 탐색기**/**데이터베이스 탐색기** 에서 **데이터 연결** 을 마우스 오른쪽 단추로 클릭 한 다음 **연결 추가**를 클릭 합니다.  
  
3. Northwind 샘플 데이터베이스에 대 한 올바른 연결을 지정 하십시오.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>LINQ to SQL 파일을 포함 하는 프로젝트를 추가 하려면  
  
1. Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다. Visual Basic **Windows Forms 응용 프로그램** 을 프로젝트 형식으로 선택 합니다.  
  
2. **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다. **LINQ to SQL 클래스** 항목 템플릿을 선택 합니다.  
  
3. 파일 이름을 `northwind.dbml`로 지정합니다. **추가**를 클릭합니다. Northwind .dbml 파일에 대해 개체 관계형 디자이너 (O/R 디자이너)가 열립니다.  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>O/R 디자이너에 쿼리할 테이블을 추가 하려면  
  
1. **서버 탐색기**/**데이터베이스 탐색기**에서 Northwind 데이터베이스에 대 한 연결을 확장 합니다. **Tables** 폴더를 확장 합니다.  
  
     O/R 디자이너를 닫은 경우 앞에서 추가한 각각의 .dbml 파일을 두 번 클릭 하 여 다시 열 수 있습니다.  
  
2. Customers 테이블을 클릭 하 고 디자이너의 왼쪽 창으로 끌어 놓습니다.  
  
     디자이너에서 프로젝트에 대 한 새 `Customer` 개체를 만듭니다. 쿼리 결과를 `Customer` 형식 또는 사용자가 만든 형식으로 프로젝션 할 수 있습니다. 이 샘플에서는 이후 절차에서 새 형식을 만들고 쿼리 결과를 해당 형식으로 프로젝션 합니다.  
  
3. 변경 내용을 저장 하 고 디자이너를 닫습니다.  
  
4. 프로젝트를 저장합니다.  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>데이터베이스를 쿼리하고 결과를 표시 하는 코드를 추가 하려면  
  
1. **도구 상자**에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 프로젝트의 기본 Windows 폼 (Form1)으로 끌어옵니다.  
  
2. Form1 클래스를 수정 하려면 Form1을 두 번 클릭 합니다.  
  
3. Form1 클래스의 `End Class` 문 뒤에 다음 코드를 추가 하 여이 샘플에 대 한 쿼리 결과를 저장할 `CustomerInfo` 형식을 만듭니다.  
  
     [!code-vb[VbLINQToSQLHowTos#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#16)]  
  
4. O/R 디자이너에 테이블을 추가 하는 경우 디자이너는 <xref:System.Data.Linq.DataContext> 개체를 프로젝트에 추가 합니다. 이 개체에는 해당 테이블에 액세스 하 고 각 테이블에 대 한 개별 개체 및 컬렉션에 액세스 하는 데 필요한 코드가 포함 되어 있습니다. 프로젝트에 대 한 <xref:System.Data.Linq.DataContext> 개체는 .dbml 파일의 이름을 기반으로 이름이 지정 됩니다. 이 프로젝트의 경우 <xref:System.Data.Linq.DataContext> 개체의 이름은 `northwindDataContext`입니다.  
  
     코드에서 <xref:System.Data.Linq.DataContext>의 인스턴스를 만들고 O/R 디자이너에 지정 된 테이블을 쿼리할 수 있습니다.  
  
     Form1 클래스의 `Load` 이벤트에서 다음 코드를 추가 하 여 데이터 컨텍스트의 속성으로 노출 되는 테이블을 쿼리 합니다. 쿼리의 `Select` 절은 쿼리 결과의 각 항목에 대해 익명 형식 대신 새 `CustomerInfo` 형식을 만듭니다.  
  
     [!code-vb[VbLINQToSQLHowTos#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#15)]  
  
5. F5 키를 눌러 프로젝트를 실행 하 고 결과를 확인 합니다.  
  
## <a name="see-also"></a>참고자료

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [쿼리](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext 메서드(O/R 디자이너)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
