---
title: '방법: 그라데이션에 감마 보정 적용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: 066ccc649105018d20cb86b6e576a1a238e0dc62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973268"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="83adc-102">방법: 그라데이션에 감마 보정 적용</span><span class="sxs-lookup"><span data-stu-id="83adc-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="83adc-103">브러시의을 설정 하 여 선형 그라데이션 브러시에 대 한 감마 보정을 사용할 수 있습니다 <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> 속성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="83adc-104">감마 보정을 사용 하지 않도록 설정 하 여 수를 <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> 속성을 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="83adc-105">감마 보정은 기본적으로 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83adc-106">예제</span><span class="sxs-lookup"><span data-stu-id="83adc-106">Example</span></span>  

<span data-ttu-id="83adc-107">컨트롤에서 호출 되는 방법은 다음 예제에서는 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-107">The following example is a method that is called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="83adc-108">선형 그라데이션 브러시를 만들고 두 사각형에 맞게 해당 브러시를 사용 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-108">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="83adc-109">첫 번째 사각형 감마 보정 하지 않고 채워지고 감마 보정을 사용 하 여 두 번째 사각형 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-109">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="83adc-110">다음 그림에서는 두 개의 채워진된 사각형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-110">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="83adc-111">감마 보정 되지 않은, 맨 위 사각형 중간에 어두운 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-111">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="83adc-112">감마 보정에는 아래 사각형 농도가 좀 더 균일에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-112">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 <span data-ttu-id="83adc-113">![Gradient](./media/gammagradient1.png "gammagradient1")</span><span class="sxs-lookup"><span data-stu-id="83adc-113">![Gradient](./media/gammagradient1.png "gammagradient1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="83adc-114">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="83adc-114">Compiling the Code</span></span>  
 <span data-ttu-id="83adc-115">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="83adc-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83adc-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="83adc-116">See also</span></span>

- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [<span data-ttu-id="83adc-117">그라데이션 브러시를 사용하여 도형 채우기</span><span class="sxs-lookup"><span data-stu-id="83adc-117">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
