---
title: 선 및 채우기 알파 혼합
ms.date: 03/30/2017
helpviewer_keywords:
- lines [Windows Forms], adding transparency
- examples [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with lines
- alpha blending
- lines [Windows Forms], alpha blending
- fills [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with fills
- shapes [Windows Forms], adding transparency
ms.assetid: 5440f48c-3ac9-44c3-b170-c1c110bdbab8
ms.openlocfilehash: 7a8286fb741effaf668b87e90da04f79d1490de2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61960942"
---
# <a name="alpha-blending-lines-and-fills"></a><span data-ttu-id="8e4a1-102">선 및 채우기 알파 혼합</span><span class="sxs-lookup"><span data-stu-id="8e4a1-102">Alpha Blending Lines and Fills</span></span>
<span data-ttu-id="8e4a1-103">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], 색은 알파, 빨강, 녹색 및 파랑에 대 한 각 8 비트를 사용 하 여 32 비트 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8e4a1-103">In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], a color is a 32-bit value with 8 bits each for alpha, red, green, and blue.</span></span> <span data-ttu-id="8e4a1-104">알파 값을 나타내는 색의 투명도-범위를 색이 배경 색과 혼합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e4a1-104">The alpha value indicates the transparency of the color — the extent to which the color is blended with the background color.</span></span> <span data-ttu-id="8e4a1-105">알파 값 범위는 0에서 255까지, 0은 완전히 투명 한 색을 나타내는 255에서 완전히 불투명 한 색을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8e4a1-105">Alpha values range from 0 through 255, where 0 represents a fully transparent color, and 255 represents a fully opaque color.</span></span>  
  
 <span data-ttu-id="8e4a1-106">알파 혼합 원본과 배경 색 데이터의 픽셀 단위로 혼합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e4a1-106">Alpha blending is a pixel-by-pixel blending of source and background color data.</span></span> <span data-ttu-id="8e4a1-107">각 세 가지 구성 요소 (빨강, 녹색, 파랑)는 지정 된 소스 색의 배경색을 다음 수식에 따라 해당 구성 요소와 혼합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e4a1-107">Each of the three components (red, green, blue) of a given source color is blended with the corresponding component of the background color according to the following formula:</span></span>  
  
 <span data-ttu-id="8e4a1-108">displayColor sourceColor × 알파 = 255 / + backgroundColor × (255 – 알파) / 255</span><span class="sxs-lookup"><span data-stu-id="8e4a1-108">displayColor = sourceColor × alpha / 255 + backgroundColor × (255 – alpha) / 255</span></span>  
  
 <span data-ttu-id="8e4a1-109">예를 들어, 소스 색의 빨강 구성 요소는 150 및 배경 색의 빨강 구성 요소는 100입니다.</span><span class="sxs-lookup"><span data-stu-id="8e4a1-109">For example, suppose the red component of the source color is 150 and the red component of the background color is 100.</span></span> <span data-ttu-id="8e4a1-110">알파 값 200 인 경우 결과 색의 빨강 구성 요소는 다음과 같이 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e4a1-110">If the alpha value is 200, the red component of the resultant color is calculated as follows:</span></span>  
  
 <span data-ttu-id="8e4a1-111">150 × 200 / 255 + 100 × (255 – 200) / 255 = 139</span><span class="sxs-lookup"><span data-stu-id="8e4a1-111">150 × 200 / 255 + 100 × (255 – 200) / 255 = 139</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8e4a1-112">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="8e4a1-112">In This Section</span></span>  
 [<span data-ttu-id="8e4a1-113">방법: 불투명 및 반투명 선 그리기</span><span class="sxs-lookup"><span data-stu-id="8e4a1-113">How to: Draw Opaque and Semitransparent Lines</span></span>](how-to-draw-opaque-and-semitransparent-lines.md)  
 <span data-ttu-id="8e4a1-114">알파 혼합 선을 그리는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8e4a1-114">Shows how to draw alpha-blended lines.</span></span>  
  
 [<span data-ttu-id="8e4a1-115">방법: 불투명 및 반투명 브러시를 사용 하 여 그리기</span><span class="sxs-lookup"><span data-stu-id="8e4a1-115">How to: Draw with Opaque and Semitransparent Brushes</span></span>](how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 <span data-ttu-id="8e4a1-116">브러시를 사용 하 여 알파 혼합 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e4a1-116">Explains how to alpha-blend with brushes.</span></span>  
  
 [<span data-ttu-id="8e4a1-117">방법: 알파 혼합 조절 하려면 혼합 모드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e4a1-117">How to: Use Compositing Mode to Control Alpha Blending</span></span>](how-to-use-compositing-mode-to-control-alpha-blending.md)  
 <span data-ttu-id="8e4a1-118">사용 하 여 알파 혼합을 제어 하는 방법에 설명 <xref:System.Drawing.Drawing2D.CompositingMode>합니다.</span><span class="sxs-lookup"><span data-stu-id="8e4a1-118">Describes how to control alpha blending using <xref:System.Drawing.Drawing2D.CompositingMode>.</span></span>  
  
 [<span data-ttu-id="8e4a1-119">방법: 색 매트릭스를 사용 하 여 이미지에 알파 값 설정</span><span class="sxs-lookup"><span data-stu-id="8e4a1-119">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>](how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 <span data-ttu-id="8e4a1-120">사용 하는 방법에 설명 된 <xref:System.Drawing.Imaging.ColorMatrix> 알파 혼합을 제어 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8e4a1-120">Explains how to use a <xref:System.Drawing.Imaging.ColorMatrix> object to control alpha blending.</span></span>
