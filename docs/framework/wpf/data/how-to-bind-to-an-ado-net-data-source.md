---
title: '방법: ADO.NET 데이터 소스 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to ADO.NET data sources
- ADO.NET data sources [WPF], binding to
- binding [WPF], to ADO.NET data sources
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
ms.openlocfilehash: 0b3d7147f45bee5e8abd95bdc51c5f5f695cf830
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458413"
---
# <a name="how-to-bind-to-an-adonet-data-source"></a><span data-ttu-id="8b160-102">방법: ADO.NET 데이터 소스 바인딩</span><span class="sxs-lookup"><span data-stu-id="8b160-102">How to: Bind to an ADO.NET Data Source</span></span>

<span data-ttu-id="8b160-103">이 예제에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> 컨트롤을 ADO.NET `DataSet`에 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8b160-103">This example shows how to bind a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> control to an ADO.NET `DataSet`.</span></span>

## <a name="example"></a><span data-ttu-id="8b160-104">예제</span><span class="sxs-lookup"><span data-stu-id="8b160-104">Example</span></span>

<span data-ttu-id="8b160-105">이 예에서는 `OleDbConnection` 개체를 사용하여 연결 문자열에 지정된 `Access MDB` 파일인 데이터 소스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="8b160-105">In this example, an `OleDbConnection` object is used to connect to the data source which is an `Access MDB` file that is specified in the connection string.</span></span> <span data-ttu-id="8b160-106">연결이 설정되고 나면 `OleDbDataAdapter` 개체가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b160-106">After the connection is established, an `OleDbDataAdapter` object is created.</span></span> <span data-ttu-id="8b160-107">`OleDbDataAdapter` 개체는 select 구조적 쿼리 언어 (SQL) 문을 실행 하 여 데이터베이스에서 레코드 집합을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b160-107">The `OleDbDataAdapter` object executes a select Structured Query Language (SQL) statement to retrieve the recordset from the database.</span></span> <span data-ttu-id="8b160-108">SQL 명령의 결과는 `OleDbDataAdapter`의 `Fill` 메서드를 호출 하 여 `DataSet` `DataTable` 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b160-108">The results from the SQL command are stored in a `DataTable` of the `DataSet` by calling the `Fill` method of the `OleDbDataAdapter`.</span></span> <span data-ttu-id="8b160-109">이 예에서 `DataTable`은 `BookTable`로 이름이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b160-109">The `DataTable` in this example is named `BookTable`.</span></span> <span data-ttu-id="8b160-110">그런 다음이 예제에서는 <xref:System.Windows.Controls.ListBox>의 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성을 `DataSet` 개체로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b160-110">The example then sets the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the <xref:System.Windows.Controls.ListBox> to the `DataSet` object.</span></span>

[!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
[!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]

<span data-ttu-id="8b160-111">그런 다음 <xref:System.Windows.Controls.ListBox>의 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성을 `DataSet``BookTable`에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b160-111">We can then bind the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to `BookTable` of the `DataSet`:</span></span>

[!code-xaml[ADODataSet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]

<span data-ttu-id="8b160-112">`BookItemTemplate`는 데이터가 표시 되는 방식을 정의 하는 <xref:System.Windows.DataTemplate>입니다.</span><span class="sxs-lookup"><span data-stu-id="8b160-112">`BookItemTemplate` is the <xref:System.Windows.DataTemplate> that defines how the data appears:</span></span>

[!code-xaml[ADODataSet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]

<span data-ttu-id="8b160-113">`IntColorConverter`는 `int`를 색상으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="8b160-113">The `IntColorConverter` converts an `int` to a color.</span></span> <span data-ttu-id="8b160-114">이 변환기를 사용 하면 `NumPages` 값이 350 보다 작은 경우 세 번째 <xref:System.Windows.Controls.TextBlock>의 <xref:System.Windows.Controls.TextBlock.Background%2A> 색은 녹색으로 표시 되 고 그렇지 않으면 빨간색으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b160-114">With the use of this converter, the <xref:System.Windows.Controls.TextBlock.Background%2A> color of the third <xref:System.Windows.Controls.TextBlock> appears green if the value of `NumPages` is less than 350 and red otherwise.</span></span> <span data-ttu-id="8b160-115">변환기의 구현은 여기에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b160-115">The implementation of the converter is not shown here.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b160-116">참조</span><span class="sxs-lookup"><span data-stu-id="8b160-116">See also</span></span>

- <xref:System.Windows.Data.BindingListCollectionView>
- [<span data-ttu-id="8b160-117">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="8b160-117">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="8b160-118">방법 항목</span><span class="sxs-lookup"><span data-stu-id="8b160-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
