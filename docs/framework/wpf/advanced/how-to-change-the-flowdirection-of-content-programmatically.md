---
title: '방법: 프로그래밍 방식으로 콘텐츠의 FlowDirection 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- FlowDirection property [WPF], changing programmatically
- documents [WPF], changing FlowDirection property programmatically
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
ms.openlocfilehash: ec159ed0efce8b5514788331e8715a55e7a8a638
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776560"
---
# <a name="how-to-change-the-flowdirection-of-content-programmatically"></a><span data-ttu-id="05e84-102">방법: 프로그래밍 방식으로 콘텐츠의 FlowDirection 변경</span><span class="sxs-lookup"><span data-stu-id="05e84-102">How to: Change the FlowDirection of Content Programmatically</span></span>
<span data-ttu-id="05e84-103">이 예제에서는 프로그래밍 방식으로 변경 하는 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 의 속성을 <xref:System.Windows.Controls.FlowDocumentReader>입니다.</span><span class="sxs-lookup"><span data-stu-id="05e84-103">This example shows how to programmatically change the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property of a <xref:System.Windows.Controls.FlowDocumentReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05e84-104">예제</span><span class="sxs-lookup"><span data-stu-id="05e84-104">Example</span></span>  
 <span data-ttu-id="05e84-105">두 개의 <xref:System.Windows.Controls.Button> 각각의 가능한 값 중 하나를 나타내는 요소는 만들어지지 <xref:System.Windows.FlowDirection>합니다.</span><span class="sxs-lookup"><span data-stu-id="05e84-105">Two <xref:System.Windows.Controls.Button> elements are created, each representing one of the possible values of <xref:System.Windows.FlowDirection>.</span></span> <span data-ttu-id="05e84-106">단추를 클릭 하 고, 연결된 된 속성 값의 내용에 적용 됩니다는 <xref:System.Windows.Controls.FlowDocumentReader> 라는 `tf1`합니다.</span><span class="sxs-lookup"><span data-stu-id="05e84-106">When a button is clicked, the associated property value is applied to the contents of a <xref:System.Windows.Controls.FlowDocumentReader> named `tf1`.</span></span>  <span data-ttu-id="05e84-107">속성 값에도 기록 됩니다는 <xref:System.Windows.Controls.TextBlock> 라는 `txt1`합니다.</span><span class="sxs-lookup"><span data-stu-id="05e84-107">The property value is also written to a <xref:System.Windows.Controls.TextBlock> named `txt1`.</span></span>  
  
 [!code-xaml[FlowDirectionSnippets#_FlowDirectionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## <a name="example"></a><span data-ttu-id="05e84-108">예제</span><span class="sxs-lookup"><span data-stu-id="05e84-108">Example</span></span>  
 <span data-ttu-id="05e84-109">위에 정의한 단추 클릭을 사용 하 여 연결 된 이벤트에서 처리 되는 C# 코드 숨김 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="05e84-109">The events associated with the button clicks defined above are handled in a C# code-behind file.</span></span>  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]
