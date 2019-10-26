---
title: L2DBForm.xaml.cs 소스 코드
ms.date: 10/22/2019
ms.topic: sample
ms.openlocfilehash: 882699a76eab3c291cd92c298287bc5d28fb08e1
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921157"
---
# <a name="l2dbformxamlcs-source-code"></a><span data-ttu-id="d29c7-102">L2DBForm.xaml.cs 소스 코드</span><span class="sxs-lookup"><span data-stu-id="d29c7-102">L2DBForm.xaml.cs source code</span></span>

<span data-ttu-id="d29c7-103">이 페이지에는 C# *L2DBForm.xaml.cs*파일의 소스 코드에 대 한 내용과 설명이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d29c7-103">This page contains the contents and description of the C# source code in the file *L2DBForm.xaml.cs*.</span></span> <span data-ttu-id="d29c7-104">이 파일에 포함된 L2XDBForm partial 클래스는 데이터 멤버와 `OnRemove` 및 `OnAddBook` 단추 클릭 이벤트 처리기라는 세 가지 논리 섹션으로 나뉠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d29c7-104">The L2XDBForm partial class contained in this file can be divided into three logical sections: data members and the `OnRemove` and `OnAddBook` button click event handlers.</span></span>

## <a name="data-members"></a><span data-ttu-id="d29c7-105">데이터 멤버</span><span class="sxs-lookup"><span data-stu-id="d29c7-105">Data members</span></span>

<span data-ttu-id="d29c7-106">두 private 데이터 멤버는 이 클래스를 *L2DBForm.xaml*에 사용되는 창 리소스와 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d29c7-106">Two private data members are used to associate this class to the window resources used in *L2DBForm.xaml*.</span></span>

- <span data-ttu-id="d29c7-107">네임스페이스 변수 `myBooks`는 `"http://www.mybooks.com"`으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="d29c7-107">The namespace variable `myBooks` is initialized to `"http://www.mybooks.com"`.</span></span>

- <span data-ttu-id="d29c7-108">`bookList` 멤버는 다음 줄을 사용하여 생성자에서 *L2DBForm.xaml*의 CDATA 문자열로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="d29c7-108">The member `bookList` is initialized in the constructor to the CDATA string in *L2DBForm.xaml* with the following line:</span></span>

    ```csharp
    bookList = (XElement)((ObjectDataProvider)Resources["LoadedBooks"]).Data;
    ```

## <a name="onaddbook-event-handler"></a><span data-ttu-id="d29c7-109">OnAddBook 이벤트 처리기</span><span class="sxs-lookup"><span data-stu-id="d29c7-109">OnAddBook event handler</span></span>

<span data-ttu-id="d29c7-110">이 메서드에는 다음 세 가지 문이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d29c7-110">This method contains the following three statements:</span></span>

- <span data-ttu-id="d29c7-111">첫 번째 조건 문은 입력 유효성 검사에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d29c7-111">The first conditional statement is used for input validation.</span></span>

- <span data-ttu-id="d29c7-112">두 번째 문은 사용자가 **Add New Book** UI(사용자 인터페이스) 섹션에서 입력한 문자열 값에서 새 <xref:System.Xml.Linq.XElement>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d29c7-112">The second statement creates a new <xref:System.Xml.Linq.XElement> from the string values the user entered in the **Add New Book** user interface (UI) section.</span></span>

- <span data-ttu-id="d29c7-113">마지막 문은 새 책 요소를 *L2DBForm.xaml*의 데이터 공급자에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d29c7-113">The last statement adds this new book element to the data provider in *L2DBForm.xaml*.</span></span> <span data-ttu-id="d29c7-114">이렇게 하면 동적 데이터 바인딩을 통해 이 새 항목으로 UI가 자동으로 업데이트되므로 사용자가 추가로 코드를 제공할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d29c7-114">Consequently, dynamic data binding will automatically update the UI with this new item; no extra user-supplied code is required.</span></span>

## <a name="onremove-event-handler"></a><span data-ttu-id="d29c7-115">OnRemove 이벤트 처리기</span><span class="sxs-lookup"><span data-stu-id="d29c7-115">OnRemove event handler</span></span>

<span data-ttu-id="d29c7-116">`OnRemove` 처리기는 두 가지 이유 때문에 `OnAddBook` 처리기보다 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="d29c7-116">The `OnRemove` handler is more complicated than the `OnAddBook` handler for two reasons.</span></span> <span data-ttu-id="d29c7-117">첫째로, 원시 XML에는 유지된 공백이 포함되어 있기 때문에 일치하는 줄 바꿈도 책 항목과 함께 제거되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d29c7-117">First, because the raw XML contains preserved white space, matching newlines must also be removed with the book entry.</span></span> <span data-ttu-id="d29c7-118">둘째로, 편리함을 위해 원하는 항목에 있던 선택 표시가 목록의 이전 항목으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d29c7-118">Second, as a convenience, the selection, which was on the deleted item, is reset to the previous one in the list.</span></span>

<span data-ttu-id="d29c7-119">그러나 선택된 책 항목을 제거하는 핵심 작업은 다음 두 명령문으로만 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d29c7-119">However, the core work of removing the selected book item is accomplished by only two statements:</span></span>

- <span data-ttu-id="d29c7-120">먼저 목록 상자에서 현재 선택된 항목과 연결된 책 요소가 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="d29c7-120">First, the book element associated with the currently selected item in the list box is retrieved:</span></span>

    ```csharp
    XElement selBook = (XElement)lbBooks.SelectedItem;
    ```

- <span data-ttu-id="d29c7-121">그런 다음 이 요소가 데이터 공급자에서 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="d29c7-121">Then, this element is deleted from the data provider:</span></span>

    ```csharp
    selBook.Remove();
    ```

<span data-ttu-id="d29c7-122">동적 데이터 바인딩을 통해 프로그램의 UI가 자동으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="d29c7-122">Again, dynamic data binding assures that the program's UI is automatically updated.</span></span>

## <a name="example"></a><span data-ttu-id="d29c7-123">예제</span><span class="sxs-lookup"><span data-stu-id="d29c7-123">Example</span></span>

### <a name="code"></a><span data-ttu-id="d29c7-124">코드</span><span class="sxs-lookup"><span data-stu-id="d29c7-124">Code</span></span>

```csharp
using System;
using System.Linq;
using System.Collections;
using System.Collections.Generic;
using System.Diagnostics;
using System.Text;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Input;
using System.Xml;
using System.Xml.Linq;

namespace LinqToXmlDataBinding {
    /// <summary>
    /// Interaction logic for L2XDBForm.xaml
    /// </summary>

    public partial class L2XDBForm : System.Windows.Window
    {
        XNamespace mybooks = "http://www.mybooks.com";
        XElement bookList;

        public L2XDBForm()
        {
            InitializeComponent();
            bookList = (XElement)((ObjectDataProvider)Resources["LoadedBooks"]).Data;
        }

        void OnRemoveBook(object sender, EventArgs e)
        {
            int index = lbBooks.SelectedIndex;
            if (index < 0) return;

            XElement selBook = (XElement)lbBooks.SelectedItem;
            //Get next node before removing element.
            XNode nextNode = selBook.NextNode;
            selBook.Remove();

            //Remove any matching newline node.
            if (nextNode != null && nextNode.ToString().Trim().Equals(""))
            { nextNode.Remove(); }

            //Set selected item.
            if (lbBooks.Items.Count > 0)
            {  lbBooks.SelectedItem = lbBooks.Items[index > 0 ? index - 1 : 0]; }
        }

        void OnAddBook(object sender, EventArgs e)
        {
            if (String.IsNullOrEmpty(tbAddID.Text) ||
                String.IsNullOrEmpty(tbAddValue.Text))
            {
                MessageBox.Show("Please supply both a Book ID and a Value!", "Entry Error!");
                return;
            }
            XElement newBook = new XElement(
                                mybooks + "book",
                                new XAttribute("id", tbAddID.Text),
                                tbAddValue.Text);
            bookList.Add("  ", newBook, "\r\n");
        }
    }
}
```

### <a name="comments"></a><span data-ttu-id="d29c7-125">주석</span><span class="sxs-lookup"><span data-stu-id="d29c7-125">Comments</span></span>

<span data-ttu-id="d29c7-126">이러한 처리기와 관련된 XAML 소스는 [L2DBForm.xaml 소스 코드](l2dbform-xaml-source-code.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d29c7-126">For the associated XAML source for these handlers, see [L2DBForm.xaml source code](l2dbform-xaml-source-code.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d29c7-127">참조</span><span class="sxs-lookup"><span data-stu-id="d29c7-127">See also</span></span>

- [<span data-ttu-id="d29c7-128">연습: LinqToXmlDataBinding 예제</span><span class="sxs-lookup"><span data-stu-id="d29c7-128">Walkthrough: LinqToXmlDataBinding example</span></span>](linq-to-xml-data-binding-sample.md)
- [<span data-ttu-id="d29c7-129">L2DBForm.xaml 소스 코드</span><span class="sxs-lookup"><span data-stu-id="d29c7-129">L2DBForm.xaml source code</span></span>](l2dbform-xaml-source-code.md)
