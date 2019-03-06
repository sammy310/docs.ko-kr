---
title: '방법: Page 함수의 반환 값 가져오기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- functions [WPF], getting return values of
- page functions [WPF], getting return values of
- return values of page functions [WPF]
- getting [WPF], return values of page functions
ms.assetid: 75470af6-256c-4c46-87e7-705080723a1c
ms.openlocfilehash: fd54a5059d028f9fc6624d1e2d03b209140b481c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365138"
---
# <a name="how-to-get-the-return-value-of-a-page-function"></a><span data-ttu-id="7b577-102">방법: Page 함수의 반환 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="7b577-102">How to: Get the Return Value of a Page Function</span></span>
<span data-ttu-id="7b577-103">이 예제에서는 페이지 함수에서 반환되는 결과를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7b577-103">This example shows how to get the result that is returned by a page function.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b577-104">예제</span><span class="sxs-lookup"><span data-stu-id="7b577-104">Example</span></span>  
 <span data-ttu-id="7b577-105">페이지 함수에서 반환 되는 결과 가져오려면 처리 해야 할 <xref:System.Windows.Navigation.PageFunction%601.Return> 페이지 함수를 호출 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="7b577-105">To get the result that is returned from a page function, you need to handle <xref:System.Windows.Navigation.PageFunction%601.Return> of the page function you are calling.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#getpagefunctionresultcodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#getpagefunctionresultcodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="7b577-106">참고자료</span><span class="sxs-lookup"><span data-stu-id="7b577-106">See also</span></span>
- <xref:System.Windows.Navigation.PageFunction%601>
