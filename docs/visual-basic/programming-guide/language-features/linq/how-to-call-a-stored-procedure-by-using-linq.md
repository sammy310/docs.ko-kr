---
title: '방법: LINQ를 사용하여 저장 프로시저 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: 7e5fecf0c4c0d3a561ec7d0c4ac03c9d9ce7f759
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075137"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a>방법: LINQ를 사용하여 저장 프로시저 호출(Visual Basic)

LINQ (통합 언어 쿼리)를 사용 하면 저장 프로시저와 같은 데이터베이스 개체를 비롯 한 데이터베이스 정보에 쉽게 액세스할 수 있습니다.  
  
 다음 예에서는 SQL Server 데이터베이스의 저장 프로시저를 호출 하는 응용 프로그램을 만드는 방법을 보여 줍니다. 이 샘플에서는 데이터베이스의 서로 다른 두 개의 저장 프로시저를 호출 하는 방법을 보여 줍니다. 각 프로시저는 쿼리 결과를 반환 합니다. 한 프로시저는 입력 매개 변수를 사용 하 고 다른 프로시저는 매개 변수를 사용 하지 않습니다.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용 합니다. 이 데이터베이스가 개발 컴퓨터에 없는 경우 Microsoft 다운로드 센터에서 다운로드할 수 있습니다. 지침은 [샘플 데이터베이스 다운로드](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)를 참조 하세요.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>데이터베이스에 대 한 연결을 만들려면  
  
1. Visual Studio의 **Server Explorer** / **Database Explorer** **Server Explorer** / **보기** 메뉴에서 서버 탐색기**데이터베이스 탐색기** 를 클릭 하 여 서버 탐색기 데이터베이스 탐색기를 엽니다.  
  
2. **서버 탐색기**데이터베이스 탐색기에서 **데이터 연결** 을 마우스 오른쪽 단추로 클릭 한 / **Database Explorer** 다음 **연결 추가**를 클릭 합니다.  
  
3. Northwind 샘플 데이터베이스에 대 한 올바른 연결을 지정 하십시오.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>LINQ to SQL 파일을 포함 하는 프로젝트를 추가 하려면  
  
1. Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다. Visual Basic **Windows Forms 응용 프로그램** 을 프로젝트 형식으로 선택 합니다.  
  
2. **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다. **LINQ to SQL 클래스** 항목 템플릿을 선택 합니다.  
  
3. 파일 이름을 `northwind.dbml`로 지정합니다. **추가**를 클릭합니다. Northwind .dbml 파일에 대해 개체 관계형 디자이너 (O/R 디자이너)가 열립니다.  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a>O/R 디자이너에 저장 프로시저를 추가 하려면  
  
1. **서버 탐색기** / **데이터베이스 탐색기**에서 Northwind 데이터베이스에 대 한 연결을 확장 합니다. **저장 프로시저** 폴더를 확장합니다.  
  
     O/R 디자이너를 닫은 경우 앞에서 추가한 각각의 .dbml 파일을 두 번 클릭 하 여 다시 열 수 있습니다.  
  
2. **연도별 매출** 저장 프로시저를 클릭 하 고 디자이너의 오른쪽 창으로 끌어 놓습니다. **가장 비싼 10 개 제품** 저장 프로시저를 클릭 하 여 디자이너의 오른쪽 창으로 끌어 놓습니다.  
  
3. 변경 내용을 저장 하 고 디자이너를 닫습니다.  
  
4. 프로젝트를 저장합니다.  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a>저장 프로시저의 결과를 표시 하는 코드를 추가 하려면  
  
1. **도구 상자**에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 프로젝트의 기본 Windows 폼, Form1에 끌어 놓습니다.  
  
2. Form1을 두 번 클릭 하 여 이벤트에 코드를 추가 `Load` 합니다.  
  
3. O/R 디자이너에 저장 프로시저를 추가 하면 디자이너에서 <xref:System.Data.Linq.DataContext> 프로젝트에 대 한 개체를 추가 합니다. 이 개체에는 해당 프로시저에 액세스 하는 데 필요한 코드가 포함 되어 있습니다. <xref:System.Data.Linq.DataContext>프로젝트에 대 한 개체는 .dbml 파일의 이름을 기반으로 이름이 지정 됩니다. 이 프로젝트의 경우 <xref:System.Data.Linq.DataContext> 개체의 이름은 `northwindDataContext` 입니다.  
  
     코드에서의 인스턴스를 만들고 <xref:System.Data.Linq.DataContext> O/R 디자이너에 지정 된 저장 프로시저 메서드를 호출할 수 있습니다. 개체에 바인딩하려면 <xref:System.Windows.Forms.DataGridView> <xref:System.Linq.Enumerable.ToList%2A> 저장 프로시저의 결과에 대해 메서드를 호출 하 여 쿼리를 즉시 실행 해야 할 수 있습니다.  
  
     이벤트에 다음 코드를 추가 `Load` 하 여 데이터 컨텍스트에 대 한 메서드로 노출 되는 저장 프로시저 중 하나를 호출 합니다.  
  
     [!code-vb[VbLINQtoSQLHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#1)]  
    [!code-vb[VbLINQtoSQLHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#2)]  
  
4. F5 키를 눌러 프로젝트를 실행 하 고 결과를 확인 합니다.  
  
## <a name="see-also"></a>참조

- [LINQ](index.md)
- [쿼리](../../../language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext 메서드(O/R 디자이너)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [방법: 저장 프로시저를 할당 하 여 업데이트, 삽입 및 삭제 수행 (O/R 디자이너)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
