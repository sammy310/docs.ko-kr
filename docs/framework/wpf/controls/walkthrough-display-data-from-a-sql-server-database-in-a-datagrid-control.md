---
title: '연습: DataGrid 컨트롤에서 SQL Server 데이터베이스의 데이터 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], displaying data from SQL Server
- controls [WPF], DataGrid
ms.assetid: 6810b048-0a23-4f86-bfa5-97f92b3cfab4
ms.openlocfilehash: 1398d8408a0b85d6603d638312e92ba35c5e77d3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591035"
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a>연습: DataGrid 컨트롤에서 SQL Server 데이터베이스의 데이터 표시

이 연습에서는 SQL Server 데이터베이스에서 데이터를 검색 하 고 컨트롤에 해당 데이터를 표시 <xref:System.Windows.Controls.DataGrid> 합니다. ADO.NET Entity Framework를 사용 하 여 데이터를 나타내는 엔터티 클래스를 만들고 LINQ를 사용 하 여 엔터티 클래스에서 지정 된 데이터를 검색 하는 쿼리를 작성 합니다.

## <a name="prerequisites"></a>사전 요구 사항

이 연습을 완료하려면 다음과 같은 구성 요소가 필요합니다.

- Visual Studio.

- AdventureWorks 예제 데이터베이스가 연결 된 SQL Server 또는 SQL Server Express의 실행 중인 인스턴스에 대 한 액세스. [GitHub](https://github.com/Microsoft/sql-server-samples/releases)에서 AdventureWorks 데이터베이스를 다운로드할 수 있습니다.

## <a name="create-entity-classes"></a>엔터티 클래스 만들기

1. Visual Basic 또는 c #에서 새 WPF 응용 프로그램 프로젝트를 만들고 이름을로 `DataGridSQLExample` 합니다.

2. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **추가**를 가리킨 다음 **새 항목**을 선택 합니다.

     새 항목 추가 대화 상자가 나타납니다.

3. 설치 된 템플릿 창에서 **데이터** 를 선택 하 고 템플릿 목록에서 **ADO.NET 엔터티 데이터 모델**를 선택 합니다.

     ![ADO.NET 엔터티 데이터 모델 항목 템플릿](../../wcf/feature-details/media/ado-net-entity-data-model-item-template.png)

4. 파일 이름을로 `AdventureWorksModel.edmx` 지정한 다음 **추가**를 클릭 합니다.

     엔터티 데이터 모델 마법사가 나타납니다.

5. 모델 콘텐츠 선택 화면에서 **데이터베이스에서 EF Designer** 를 선택 하 고 **다음**을 클릭 합니다.

6. 데이터 연결 선택 화면에서 AdventureWorksLT2008 데이터베이스에 대 한 연결을 제공 합니다. 자세한 내용은 [데이터 연결 선택 대화 상자](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399244(v=vs.100))를 참조 하세요.

    이름이이 `AdventureWorksLT2008Entities` 고 **다른 이름으로 app.config의 엔터티 연결 설정 저장** 확인란이 선택 되어 있는지 확인 하 고 **다음**을 클릭 합니다.

7. 데이터베이스 개체 선택 화면에서 테이블 노드를 확장 하 고 **제품 및 제품** **범주** 테이블을 선택 합니다.

     모든 테이블에 대 한 엔터티 클래스를 생성할 수 있습니다. 그러나이 예에서는 이러한 두 테이블 에서만 데이터를 검색 합니다.

     ![테이블에서 Product 및 ProductCategory 선택](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")

8. **Finish**를 클릭합니다.

     제품 및 상품 범주 엔터티는 Entity Designer 표시 됩니다.

     ![Product 및 ProductCategory 엔터티 모델](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")

## <a name="retrieve-and-present-the-data"></a>데이터 검색 및 표시

1. Mainwindow.xaml 파일을 엽니다.

2. 의 <xref:System.Windows.FrameworkElement.Width%2A> 속성을 <xref:System.Windows.Window> 450로 설정 합니다.

3. XAML 편집기에서 <xref:System.Windows.Controls.DataGrid> 및 태그 사이에 다음 태그를 추가 `<Grid>` 하 여 `</Grid>` 라는를 추가 <xref:System.Windows.Controls.DataGrid> 합니다 `dataGrid1` .

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]

     ![DataGrid가 있는 창](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")

4. <xref:System.Windows.Window>를 선택합니다.

5. 속성 창 또는 XAML 편집기를 사용 하 여 <xref:System.Windows.Window> 이벤트에 대해 명명 된에 대 한 이벤트 처리기를 만듭니다 `Window_Loaded` <xref:System.Windows.FrameworkElement.Loaded> . 자세한 내용은 [방법: 간단한 이벤트 처리기 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))를 참조 하세요.

     다음은 Mainwindow.xaml에 대 한 XAML을 보여 줍니다.

    > [!NOTE]
    > Visual Basic를 사용 하는 경우 Mainwindow.xaml의 첫 번째 줄에서을 `x:Class="DataGridSQLExample.MainWindow"` 로 바꿉니다 `x:Class="MainWindow"` .

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]

6. 에 대 한 코드 숨겨진 파일 (Mainwindow.xaml 또는 MainWindow.xaml.cs)을 엽니다 <xref:System.Windows.Window> .

7. 조인 된 테이블에서 특정 값만 검색 하 고 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 의 속성을 쿼리 결과로 설정 하려면 다음 코드를 추가 합니다 <xref:System.Windows.Controls.DataGrid> .

     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]

8. 예제를 실행합니다.

     데이터를 표시 하는가 표시 되어야 합니다 <xref:System.Windows.Controls.DataGrid> .

     ![SQL 데이터베이스의 데이터가 있는 DataGrid](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.DataGrid>
