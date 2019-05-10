---
title: '방법: 혼합 모드를 사용하여 알파 혼합 조절'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
ms.openlocfilehash: ad9437d9c250f067f26f61638b66fbc30fa3b599
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623925"
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a><span data-ttu-id="cbdc0-102">방법: 혼합 모드를 사용하여 알파 혼합 조절</span><span class="sxs-lookup"><span data-stu-id="cbdc0-102">How to: Use Compositing Mode to Control Alpha Blending</span></span>
<span data-ttu-id="cbdc0-103">다음 특성을 가진 오프 스크린 비트맵을 만들려고 하는 상황이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbdc0-103">There may be times when you want to create an off-screen bitmap that has the following characteristics:</span></span>  
  
- <span data-ttu-id="cbdc0-104">색의 알파 값을 255 보다 작은 경우</span><span class="sxs-lookup"><span data-stu-id="cbdc0-104">Colors have alpha values that are less than 255.</span></span>  
  
- <span data-ttu-id="cbdc0-105">색은 알파 비트맵을 만들 때 서로 혼합 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbdc0-105">Colors are not alpha blended with each other as you create the bitmap.</span></span>  
  
- <span data-ttu-id="cbdc0-106">완성 된 비트맵을 표시 하는 경우 비트맵 색 디스플레이 장치에서 배경 색과 혼합 된 알파가입니다.</span><span class="sxs-lookup"><span data-stu-id="cbdc0-106">When you display the finished bitmap, colors in the bitmap are alpha blended with the background colors on the display device.</span></span>  
  
 <span data-ttu-id="cbdc0-107">이러한 비트맵을 만들려면 빈 생성 <xref:System.Drawing.Bitmap> 개체를 생성 한 다음는 <xref:System.Drawing.Graphics> 해당 비트맵을 기반으로 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cbdc0-107">To create such a bitmap, construct a blank <xref:System.Drawing.Bitmap> object, and then construct a <xref:System.Drawing.Graphics> object based on that bitmap.</span></span> <span data-ttu-id="cbdc0-108">혼합 모드를 설정 합니다 <xref:System.Drawing.Graphics> 개체를 <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="cbdc0-108">Set the compositing mode of the <xref:System.Drawing.Graphics> object to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbdc0-109">예제</span><span class="sxs-lookup"><span data-stu-id="cbdc0-109">Example</span></span>  
 <span data-ttu-id="cbdc0-110">다음 예에서는 <xref:System.Drawing.Graphics> 기준으로 개체를 <xref:System.Drawing.Bitmap> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cbdc0-110">The following example creates a <xref:System.Drawing.Graphics> object based on a <xref:System.Drawing.Bitmap> object.</span></span> <span data-ttu-id="cbdc0-111">코드를 사용 하는 <xref:System.Drawing.Graphics> 두 반투명 브러시와 함께 개체 (알파 = 160) 비트맵에 그릴 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbdc0-111">The code uses the <xref:System.Drawing.Graphics> object along with two semitransparent brushes (alpha = 160) to paint on the bitmap.</span></span> <span data-ttu-id="cbdc0-112">코드는 빨간색 타원을 및 반투명 브러시를 사용 하 여 녹색 타원을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="cbdc0-112">The code fills a red ellipse and a green ellipse using the semitransparent brushes.</span></span> <span data-ttu-id="cbdc0-113">녹색 타원 겹치는 빨간색 타원 있지만 때문에 녹색 빨간색 혼합 되지는 않습니다의 합성 모드를 <xref:System.Drawing.Graphics> 개체를로 <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>합니다.</span><span class="sxs-lookup"><span data-stu-id="cbdc0-113">The green ellipse overlaps the red ellipse, but the green is not blended with the red because the compositing mode of the <xref:System.Drawing.Graphics> object is set to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.</span></span>  
  
 <span data-ttu-id="cbdc0-114">코드를 화면에 두 번 비트맵을 그립니다: 및 한 번 컬러 배경에 흰색 배경에서 한 번입니다.</span><span class="sxs-lookup"><span data-stu-id="cbdc0-114">The code draws the bitmap on the screen twice: once on a white background and once on a multicolored background.</span></span> <span data-ttu-id="cbdc0-115">타원 두 개의 포함 된 비트맵의 픽셀 160, 알파 구성 요소가 없으므로 화면의 배경 색과 혼합 되는 줄임표 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbdc0-115">The pixels in the bitmap that are part of the two ellipses have an alpha component of 160, so the ellipses are blended with the background colors on the screen.</span></span>  
  
 <span data-ttu-id="cbdc0-116">다음 그림에서는 코드 예제의 출력을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbdc0-116">The following illustration shows the output of the code example.</span></span> <span data-ttu-id="cbdc0-117">줄임표는 백그라운드와 혼합 되어 있지만 서로 혼합 하지 되는 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbdc0-117">Note that the ellipses are blended with the background, but they are not blended with each other.</span></span>  
  
 ![다이어그램 표시 줄임표 하지 서로 배경색과 혼합 됩니다.](./media/how-to-use-compositing-mode-to-control-alpha-blending/ellipses-blended-background.png)  
  
 <span data-ttu-id="cbdc0-119">이 문을 포함 하는 코드 예제:</span><span class="sxs-lookup"><span data-stu-id="cbdc0-119">The code example contains this statement:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 <span data-ttu-id="cbdc0-120">배경 물론 서로 혼합 수에 있는 줄임표를 하려는 경우 해당 문을 다음과 변경:</span><span class="sxs-lookup"><span data-stu-id="cbdc0-120">If you want the ellipses to be blended with each other as well as with the background, change that statement to the following:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 <span data-ttu-id="cbdc0-121">다음 그림에서는 수정 된 코드의 출력을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbdc0-121">The following illustration shows the output of the revised code.</span></span>  
  
 ![줄임표를 보여주는 다이어그램 배경을 사용 하 여 함께 혼합 됩니다.](./media/how-to-use-compositing-mode-to-control-alpha-blending/blend-ellipses-background.png)  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cbdc0-123">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="cbdc0-123">Compiling the Code</span></span>  
 <span data-ttu-id="cbdc0-124">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs>의 매개 변수인 `e`<xref:System.Windows.Forms.PaintEventHandler>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cbdc0-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbdc0-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="cbdc0-125">See also</span></span>

- <xref:System.Drawing.Color.FromArgb%2A>
- [<span data-ttu-id="cbdc0-126">선 및 채우기 알파 혼합</span><span class="sxs-lookup"><span data-stu-id="cbdc0-126">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
