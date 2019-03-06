---
title: '방법: 이미지가 있는 단추 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
ms.openlocfilehash: fe9f35a6f83c5a839823d94c4d3c55e01b192fb1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352037"
---
# <a name="how-to-create-a-button-that-has-an-image"></a><span data-ttu-id="0f601-102">방법: 이미지가 있는 단추 만들기</span><span class="sxs-lookup"><span data-stu-id="0f601-102">How to: Create a Button That Has an Image</span></span>
<span data-ttu-id="0f601-103">이 예제에서 이미지를 포함 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.Button>합니다.</span><span class="sxs-lookup"><span data-stu-id="0f601-103">This example shows how to include an image on a <xref:System.Windows.Controls.Button>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f601-104">예제</span><span class="sxs-lookup"><span data-stu-id="0f601-104">Example</span></span>  
 <span data-ttu-id="0f601-105">다음 예제에서는 두 개의 <xref:System.Windows.Controls.Button> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="0f601-105">The following example creates two <xref:System.Windows.Controls.Button> controls.</span></span> <span data-ttu-id="0f601-106">하나의 <xref:System.Windows.Controls.Button> 텍스트가 이미지를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f601-106">One <xref:System.Windows.Controls.Button> contains text and the other contains an image.</span></span> <span data-ttu-id="0f601-107">예제의 프로젝트 폴더의 하위 데이터 라는 폴더에 이미지가입니다.</span><span class="sxs-lookup"><span data-stu-id="0f601-107">The image is in a folder called data, which is a subfolder of the example’s project folder.</span></span> <span data-ttu-id="0f601-108">클릭할 때 합니다 <xref:System.Windows.Controls.Button> 이미지, 백그라운드 및 다른 텍스트 있는 <xref:System.Windows.Controls.Button> 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f601-108">When a user clicks the <xref:System.Windows.Controls.Button> that has the image, the background and the text of the other <xref:System.Windows.Controls.Button> change.</span></span>  
  
 <span data-ttu-id="0f601-109">이 예제에서는 <xref:System.Windows.Controls.Button> 태그를 사용 하 여 제어 하지만 코드를 사용 하 여 작성 된 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="0f601-109">This example creates <xref:System.Windows.Controls.Button> controls by using markup but uses code to write the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handlers.</span></span>  
  
 [!code-xaml[BtnColor#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="0f601-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="0f601-110">See also</span></span>
- [<span data-ttu-id="0f601-111">컨트롤</span><span class="sxs-lookup"><span data-stu-id="0f601-111">Controls</span></span>](index.md)
- [<span data-ttu-id="0f601-112">컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="0f601-112">Control Library</span></span>](control-library.md)
