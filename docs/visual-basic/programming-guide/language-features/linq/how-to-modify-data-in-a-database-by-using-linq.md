---
description: '자세한 정보: 방법: LINQ를 사용 하 여 데이터베이스의 데이터 수정 (Visual Basic)'
title: '방법: LINQ를 사용하여 데이터베이스의 데이터 수정'
ms.date: 07/20/2015
helpviewer_keywords:
- inserting rows [LINQ to SQL]
- deleting rows [LINQ to SQL]
- updating rows [LINQ to SQL]
- inserting data [Visual Basic]
- deleting data
- data [Visual Basic], updating
- updating data [LINQ]
- queries [LINQ in Visual Basic], data changes in database
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: cf52635f-0c1b-46c3-aff1-bdf181cf19b1
ms.openlocfilehash: b58ca542fbc6f4d63705e45b53edc8ded83ab88b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100422772"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a>방법: LINQ를 사용하여 데이터베이스의 데이터 수정(Visual Basic)

LINQ (Language-Integrated Query) 쿼리를 사용 하면 데이터베이스 정보에 액세스 하 고 데이터베이스의 값을 쉽게 수정할 수 있습니다.

다음 예에서는 SQL Server 데이터베이스에서 정보를 검색 하 고 업데이트 하는 새 응용 프로그램을 만드는 방법을 보여 줍니다.

이 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용 합니다. 이 데이터베이스가 개발 컴퓨터에 없는 경우 Microsoft 다운로드 센터에서 다운로드할 수 있습니다. 지침은 [샘플 데이터베이스 다운로드](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)를 참조 하세요.

### <a name="to-create-a-connection-to-a-database"></a>데이터베이스에 대 한 연결을 만들려면

1. Visual Studio에서  / **보기** 메뉴를 클릭 한 다음 **서버 탐색기** 데이터베이스 탐색기을 선택 하 여 서버 탐색기 **데이터베이스 탐색기** 를 엽니다 / .

2. **서버 탐색기** 데이터베이스 탐색기에서 **데이터 연결** 을 마우스 오른쪽 단추로 클릭 / 하 고 **연결 추가** 를 클릭 합니다.

3. Northwind 샘플 데이터베이스에 대 한 올바른 연결을 지정 하십시오.

### <a name="to-add-a-project-with-a-linq-to-sql-file"></a>LINQ to SQL 파일을 사용 하 여 프로젝트를 추가 하려면

1. Visual Studio의 **파일** 메뉴에서 **새로 만들기** 를 가리킨 다음 **프로젝트** 를 클릭합니다. Visual Basic **Windows Forms 응용 프로그램** 을 프로젝트 형식으로 선택 합니다.

2. **프로젝트** 메뉴에서 **새 항목 추가** 를 클릭합니다. **LINQ to SQL 클래스** 항목 템플릿을 선택 합니다.

3. 파일 이름을 `northwind.dbml`로 지정합니다. **추가** 를 클릭합니다. 파일에 대 한 개체 관계형 디자이너 (O/R 디자이너)가 열립니다 `northwind.dbml` .

### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a>쿼리에 테이블을 추가 하 고 디자이너에 수정 하려면

1. **서버 탐색기** / **데이터베이스 탐색기** 에서 Northwind 데이터베이스에 대 한 연결을 확장 합니다. **테이블** 폴더를 확장합니다.

     O/R 디자이너를 닫은 경우 앞에서 추가한 파일을 두 번 클릭 하 여 다시 열 수 있습니다 `northwind.dbml` .

2. Customers 테이블을 클릭 하 고 디자이너의 왼쪽 창으로 끌어 놓습니다.

     디자이너에서 프로젝트에 대 한 새 Customer 개체를 만듭니다.

3. 변경 내용을 저장 하 고 디자이너를 닫습니다.

4. 프로젝트를 저장합니다.

### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a>데이터베이스를 수정 하 고 결과를 표시 하는 코드를 추가 하려면

1. **도구 상자** 에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 프로젝트의 기본 Windows 폼, Form1에 끌어 놓습니다.

2. O/R 디자이너에 테이블을 추가 하면 디자이너에서 <xref:System.Data.Linq.DataContext> 개체를 프로젝트에 추가 합니다. 이 개체에는 Customers 테이블에 액세스 하는 데 사용할 수 있는 코드가 포함 되어 있습니다. 또한 테이블에 대 한 로컬 고객 개체와 Customers 컬렉션을 정의 하는 코드도 포함 됩니다. <xref:System.Data.Linq.DataContext>프로젝트에 대 한 개체는 .dbml 파일의 이름을 기반으로 이름이 지정 됩니다. 이 프로젝트의 경우 <xref:System.Data.Linq.DataContext> 개체의 이름은 `northwindDataContext` 입니다.

     코드에서 개체의 인스턴스를 만들고 <xref:System.Data.Linq.DataContext> O/R 디자이너에서 지정한 Customers 컬렉션을 쿼리하고 수정할 수 있습니다. Customers 컬렉션에 대 한 변경 내용은 개체의 메서드를 호출 하 여 제출할 때까지 데이터베이스에 반영 되지 않습니다 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> <xref:System.Data.Linq.DataContext> .

     Windows Form Form1을 두 번 클릭 하 여 <xref:System.Windows.Forms.Form.Load> 의 속성으로 노출 되는 Customers 테이블을 쿼리 하는 코드를 이벤트에 추가 합니다 <xref:System.Data.Linq.DataContext> . 다음 코드를 추가합니다.

    ```vb
    Private db As northwindDataContext

    Private Sub Form1_Load(ByVal sender As System.Object,
                           ByVal e As System.EventArgs
                          ) Handles MyBase.Load
      db = New northwindDataContext()

      RefreshData()
    End Sub

    Private Sub RefreshData()
      Dim customers = From cust In db.Customers
                      Where cust.City(0) = "W"
                      Select cust

      DataGridView1.DataSource = customers
    End Sub
    ```

3. **도구 상자** 에서 세 컨트롤을 <xref:System.Windows.Forms.Button> 폼으로 끌어옵니다. 첫 번째 컨트롤을 선택 `Button` 합니다. **속성** 창에서 컨트롤의를로 설정 하 `Name` `Button` `AddButton` 고 `Text` 를로 설정 합니다 `Add` . 두 번째 단추를 선택 하 고 속성을로 설정 하 고 속성을로 설정 합니다 `Name` `UpdateButton` `Text` `Update` . 세 번째 단추를 선택 하 고 속성을로 설정 하 고 속성을로 설정 합니다 `Name` `DeleteButton` `Text` `Delete` .

4. **추가** 단추를 두 번 클릭 하 여 해당 이벤트에 코드를 추가 `Click` 합니다. 다음 코드를 추가합니다.

    ```vb
    Private Sub AddButton_Click(ByVal sender As System.Object,
                                ByVal e As System.EventArgs
                               ) Handles AddButton.Click
      Dim cust As New Customer With {
        .City = "Wellington",
        .CompanyName = "Blue Yonder Airlines",
        .ContactName = "Jill Frank",
        .Country = "New Zealand",
        .CustomerID = "JILLF"}

      db.Customers.InsertOnSubmit(cust)

      Try
        db.SubmitChanges()
      Catch
        ' Handle exception.
      End Try

      RefreshData()
    End Sub
    ```

5. **업데이트** 단추를 두 번 클릭 하 여 해당 이벤트에 코드를 추가 `Click` 합니다. 다음 코드를 추가합니다.

    ```vb
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _
                                   ByVal e As System.EventArgs
                                  ) Handles UpdateButton.Click
      Dim updateCust = (From cust In db.Customers
                        Where cust.CustomerID = "JILLF").ToList()(0)

      updateCust.ContactName = "Jill Shrader"
      updateCust.Country = "Wales"
      updateCust.CompanyName = "Red Yonder Airlines"
      updateCust.City = "Cardiff"

      Try
        db.SubmitChanges()
      Catch
        ' Handle exception.
      End Try

      RefreshData()
    End Sub
    ```

6. **삭제** 단추를 두 번 클릭 하 여 해당 이벤트에 코드를 추가 `Click` 합니다. 다음 코드를 추가합니다.

    ```vb
    Private Sub DeleteButton_Click(ByVal sender As System.Object, _
                                   ByVal e As System.EventArgs
                                  ) Handles DeleteButton.Click
      Dim deleteCust = (From cust In db.Customers
                        Where cust.CustomerID = "JILLF").ToList()(0)

      db.Customers.DeleteOnSubmit(deleteCust)

      Try
        db.SubmitChanges()
      Catch
        ' Handle exception.
      End Try

      RefreshData()
    End Sub
    ```

7. F5 키를 눌러 프로젝트를 실행합니다. **추가** 를 클릭 하 여 새 레코드를 추가 합니다. **업데이트** 를 클릭 하 여 새 레코드를 수정 합니다. **삭제** 를 클릭 하 여 새 레코드를 삭제 합니다.

## <a name="see-also"></a>참고 항목

- [LINQ](index.md)
- [쿼리](../../../language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext 메서드(O/R 디자이너)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [방법: 저장 프로시저를 할당 하 여 업데이트, 삽입 및 삭제 수행 (O/R 디자이너)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
