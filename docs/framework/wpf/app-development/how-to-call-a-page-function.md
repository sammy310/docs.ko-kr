---
title: '방법: 페이지 함수 호출'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- calling page functions [WPF]
- page functions [WPF], calling
- functions [WPF], calling
ms.assetid: a4808397-c6d5-406a-83e0-0091f0c15ae4
ms.openlocfilehash: fb58d50a63cca41420aa102ca0c8b63f3b14c0d6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62006735"
---
# <a name="how-to-call-a-page-function"></a><span data-ttu-id="0478f-102">방법: 페이지 함수 호출</span><span class="sxs-lookup"><span data-stu-id="0478f-102">How to: Call a Page Function</span></span>
<span data-ttu-id="0478f-103">페이지 함수를 호출 하는 방법을 보여 주는이 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="0478f-103">This example shows how to call a page function from a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0478f-104">예제</span><span class="sxs-lookup"><span data-stu-id="0478f-104">Example</span></span>  
 <span data-ttu-id="0478f-105">사용 하 여 페이지 함수를 이동할 수는 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]마찬가지로 페이지를 탐색할 때 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0478f-105">You can navigate to a page function using a [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], just as you can when you navigate to a page.</span></span> <span data-ttu-id="0478f-106">다음 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0478f-106">This is shown in the following example.</span></span>  
  
 [!code-csharp[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#navigatetoapagefunctionlikeapagecodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#navigatetoapagefunctionlikeapagecodebehind)]  
  
 <span data-ttu-id="0478f-107">데이터를 페이지 함수에 전달해야 하는 경우 인스턴스를 만든 다음 속성을 설정하여 데이터를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0478f-107">If you need to pass data to the page function, you can create an instance of it and pass the data by setting a property.</span></span> <span data-ttu-id="0478f-108">또는 다음 예에 표시된 대로 기본이 아닌 생성자를 사용하여 데이터를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0478f-108">Or, as the following example shows, you can pass the data using a non-default constructor.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#callapagefunctioncodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#callapagefunctioncodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="0478f-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="0478f-109">See also</span></span>

- <xref:System.Windows.Navigation.PageFunction%601>
