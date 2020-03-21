---
title: 세 가지 범주의 그래픽 서비스
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: b0f2ad8293daf6ad53899a0f8be82985c24ff50d
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111207"
---
# <a name="three-categories-of-graphics-services"></a><span data-ttu-id="820d1-102">세 가지 범주의 그래픽 서비스</span><span class="sxs-lookup"><span data-stu-id="820d1-102">Three Categories of Graphics Services</span></span>
<span data-ttu-id="820d1-103">Windows Forms의 그래픽 제품은 다음과 같은 세 가지 광범위한 범주에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="820d1-103">The graphics offerings in Windows Forms fall into the following three broad categories:</span></span>  
  
- <span data-ttu-id="820d1-104">2차원(2차원) 벡터 그래픽</span><span class="sxs-lookup"><span data-stu-id="820d1-104">Two-dimensional (2-D) vector graphics</span></span>  
  
- <span data-ttu-id="820d1-105">이미징</span><span class="sxs-lookup"><span data-stu-id="820d1-105">Imaging</span></span>  
  
- <span data-ttu-id="820d1-106">입력 체계</span><span class="sxs-lookup"><span data-stu-id="820d1-106">Typography</span></span>  
  
## <a name="2d-vector-graphics"></a><span data-ttu-id="820d1-107">2D 벡터 그래픽</span><span class="sxs-lookup"><span data-stu-id="820d1-107">2D Vector Graphics</span></span>  
 <span data-ttu-id="820d1-108">2차원 벡터 그래픽은 기본입니다. 선, 곡선 및 그림과 같은; 좌표계의 점 집합에 의해 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="820d1-108">Two-dimensional vector graphics are primitives; such as lines, curves, and figures; that are specified by sets of points on a coordinate system.</span></span> <span data-ttu-id="820d1-109">예를 들어 직선은 두 끝점에 의해 지정되고 사각형은 왼쪽 위 모서리의 위치를 지정하는 점과 너비와 높이를 주는 숫자 쌍으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="820d1-109">For example, a straight line is specified by its two endpoints, and a rectangle is specified by a point giving the location of its upper-left corner and a pair of numbers giving its width and height.</span></span> <span data-ttu-id="820d1-110">단순 패스는 직선으로 연결된 점의 배열에 의해 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="820d1-110">A simple path is specified by an array of points that are connected by straight lines.</span></span> <span data-ttu-id="820d1-111">베지어 스플래라인은 4개의 컨트롤 포인트로 지정된 정교한 곡선입니다.</span><span class="sxs-lookup"><span data-stu-id="820d1-111">A Bézier spline is a sophisticated curve specified by four control points.</span></span>  
  
 <span data-ttu-id="820d1-112">GDI+는 프리미티브 자체에 대한 정보를 저장하는 클래스및 구조, 기본 요소를 그리는 방법에 대한 정보를 저장하는 클래스 및 실제로 도면을 수행하는 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="820d1-112">GDI+ provides classes and structures that store information about the primitives themselves, classes that store information about how the primitives will be drawn, and classes that actually do the drawing.</span></span> <span data-ttu-id="820d1-113">예를 들어, <xref:System.Drawing.Rectangle> 구조는 사각형의 위치와 크기를 저장합니다. 클래스는 <xref:System.Drawing.Pen> 선 색상, 선 너비 및 선 스타일에 대한 정보를 저장합니다. <xref:System.Drawing.Graphics> 클래스에는 선, 사각형, 패스 및 기타 그림을 그리는 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="820d1-113">For example, the <xref:System.Drawing.Rectangle> structure stores the location and size of a rectangle; the <xref:System.Drawing.Pen> class stores information about line color, line width, and line style; and the <xref:System.Drawing.Graphics> class has methods for drawing lines, rectangles, paths, and other figures.</span></span> <span data-ttu-id="820d1-114">닫힌 그림과 <xref:System.Drawing.Brush> 패스가 색상이나 패턴으로 채워지는 방법에 대한 정보를 저장하는 여러 클래스도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="820d1-114">There are also several <xref:System.Drawing.Brush> classes that store information about how closed figures and paths will be filled with colors or patterns.</span></span>  
  
 <span data-ttu-id="820d1-115">그래픽 명령 시퀀스인 벡터 이미지를 메타파일로 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="820d1-115">You can record a vector image, which is a sequence of graphics commands, in a metafile.</span></span> <span data-ttu-id="820d1-116">GDI+는 <xref:System.Drawing.Imaging.Metafile> 메타파일을 기록, 표시 및 저장하기 위한 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="820d1-116">GDI+ provides the <xref:System.Drawing.Imaging.Metafile> class for recording, displaying, and saving metafiles.</span></span> <span data-ttu-id="820d1-117"><xref:System.Drawing.Imaging.MetafileHeader> 및 <xref:System.Drawing.Imaging.MetaHeader> 클래스를 사용하여 메타파일 헤더에 저장된 데이터를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="820d1-117">With the <xref:System.Drawing.Imaging.MetafileHeader> and <xref:System.Drawing.Imaging.MetaHeader> classes, you can inspect the data stored in a metafile header.</span></span>  
  
## <a name="imaging"></a><span data-ttu-id="820d1-118">이미징</span><span class="sxs-lookup"><span data-stu-id="820d1-118">Imaging</span></span>  
 <span data-ttu-id="820d1-119">특정 종류의 사진은 벡터 그래픽 기술로 표시하기가 어렵거나 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="820d1-119">Certain kinds of pictures are difficult or impossible to display with the techniques of vector graphics.</span></span> <span data-ttu-id="820d1-120">예를 들어 도구 모음 단추의 그림과 아이콘으로 표시되는 그림은 선과 곡선의 컬렉션으로 지정하기 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="820d1-120">For example, the pictures on toolbar buttons and the pictures that appear as icons are difficult to specify as collections of lines and curves.</span></span> <span data-ttu-id="820d1-121">붐비는 야구장의 고해상도 디지털 사진은 벡터 기술로 제작하기가 훨씬 더 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="820d1-121">A high-resolution digital photograph of a crowded baseball stadium is even more difficult to create with vector techniques.</span></span> <span data-ttu-id="820d1-122">이 유형의 이미지는 비트맵으로 저장되며, 이 배열은 화면에서 개별 점의 색상을 나타내는 숫자 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="820d1-122">Images of this type are stored as bitmaps, which are arrays of numbers that represent the colors of individual dots on the screen.</span></span> <span data-ttu-id="820d1-123">GDI+는 <xref:System.Drawing.Bitmap> 비트맵을 표시, 조작 및 저장하기 위한 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="820d1-123">GDI+ provides the <xref:System.Drawing.Bitmap> class for displaying, manipulating, and saving bitmaps.</span></span>  
  
## <a name="typography"></a><span data-ttu-id="820d1-124">입력 체계</span><span class="sxs-lookup"><span data-stu-id="820d1-124">Typography</span></span>  
 <span data-ttu-id="820d1-125">타이포그래피는 다양한 글꼴, 크기 및 스타일로 텍스트를 표시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="820d1-125">Typography is the display of text in a variety of fonts, sizes, and styles.</span></span> <span data-ttu-id="820d1-126">GDI+는 이 복잡한 작업에 대한 광범위한 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="820d1-126">GDI+ provides extensive support for this complex task.</span></span> <span data-ttu-id="820d1-127">GDI+의 새로운 기능 중 하나는 LCD 화면에서 렌더링된 텍스트를 더 매끄러운 모양으로 만드는 서브픽셀 안티앨리어싱입니다.</span><span class="sxs-lookup"><span data-stu-id="820d1-127">One of the new features in GDI+ is subpixel antialiasing, which gives text rendered on an LCD screen a smoother appearance.</span></span>  
  
 <span data-ttu-id="820d1-128">또한 Windows Forms는 <xref:System.Windows.Forms.TextRenderer> 동급에서 GDI 기능이 있는 텍스트를 그리는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="820d1-128">In addition, Windows Forms offers the option to draw text with GDI capabilities in its <xref:System.Windows.Forms.TextRenderer> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="820d1-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="820d1-129">See also</span></span>

- [<span data-ttu-id="820d1-130">그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="820d1-130">Graphics Overview</span></span>](graphics-overview-windows-forms.md)
- [<span data-ttu-id="820d1-131">GDI+ 관리 코드 정보</span><span class="sxs-lookup"><span data-stu-id="820d1-131">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)
- [<span data-ttu-id="820d1-132">관리되는 그래픽 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="820d1-132">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)
