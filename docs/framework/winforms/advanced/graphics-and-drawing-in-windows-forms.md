---
title: Windows Forms의 그래픽 및 그리기
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 08f87436ade62bb54295b012a1c24dc177ea9667
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938179"
---
# <a name="graphics-and-drawing-in-windows-forms"></a><span data-ttu-id="f0ae0-102">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="f0ae0-102">Graphics and Drawing in Windows Forms</span></span>
<span data-ttu-id="f0ae0-103">공용 언어 런타임에서는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]라는 Windows [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)](그래픽 디바이스 인터페이스)의 고급 구현을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ae0-103">The common language runtime uses an advanced implementation of the Windows Graphics Device Interface ([!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]) called [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="f0ae0-104">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]를 통해 그래픽을 만들고, 텍스트를 그리고, 그래픽 이미지를 개체로 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ae0-104">With [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] you can create graphics, draw text, and manipulate graphical images as objects.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="f0ae0-105">는 성능과 사용 편의성을 제공하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ae0-105">is designed to offer performance and ease of use.</span></span> <span data-ttu-id="f0ae0-106">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]를 사용하여 Windows Forms 및 컨트롤에 그래픽 이미지를 렌더링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ae0-106">You can use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to render graphical images on Windows Forms and controls.</span></span> <span data-ttu-id="f0ae0-107">Web Forms에서 직접 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]를 사용할 수는 없지만 이미지 웹 서버 컨트롤을 통해 그래픽 이미지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ae0-107">Although you cannot use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] directly on Web Forms, you can display graphical images through the Image Web Server control.</span></span>  
  
 <span data-ttu-id="f0ae0-108">이 섹션에는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 프로그래밍의 기본 사항을 소개하는 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ae0-108">In this section, you will find topics that introduce the fundamentals of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] programming.</span></span> <span data-ttu-id="f0ae0-109">포괄적인 참조는 아니지만 이 섹션은 <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> 및 <xref:System.Drawing.Color> 개체에 대한 정보를 포함하며 도형 그리기, 텍스트 그리기 또는 이미지 표시와 같은 작업을 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ae0-109">Although not intended to be a comprehensive reference, this section includes information about the <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, and <xref:System.Drawing.Color> objects, and explains how to perform such tasks as drawing shapes, drawing text, or displaying images.</span></span> <span data-ttu-id="f0ae0-110">자세한 내용은 [GDI + 참조](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference)합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ae0-110">For more information, see [GDI+ Reference](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span></span>  
  
 <span data-ttu-id="f0ae0-111">바로 시작하려면 [그래픽 프로그래밍 시작](getting-started-with-graphics-programming.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0ae0-111">If you'd like to jump in and get started right away, see [Getting Started with Graphics Programming](getting-started-with-graphics-programming.md).</span></span> <span data-ttu-id="f0ae0-112">Windows Forms에서 코드를 사용하여 선, 도형, 텍스트 등을 그리는 방법에 대한 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ae0-112">It has topics on how to use code to draw lines, shapes, text, and more on Windows forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f0ae0-113">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="f0ae0-113">In This Section</span></span>  
 [<span data-ttu-id="f0ae0-114">그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="f0ae0-114">Graphics Overview</span></span>](graphics-overview-windows-forms.md)  
 <span data-ttu-id="f0ae0-115">그래픽 관련 관리되는 클래스를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ae0-115">Provides an introduction to the graphics-related managed classes.</span></span>  
  
 [<span data-ttu-id="f0ae0-116">GDI + 관리 코드 정보</span><span class="sxs-lookup"><span data-stu-id="f0ae0-116">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
 <span data-ttu-id="f0ae0-117">관리되는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 클래스에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ae0-117">Provides information about the managed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes.</span></span>  
  
 [<span data-ttu-id="f0ae0-118">관리되는 그래픽 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="f0ae0-118">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)  
 <span data-ttu-id="f0ae0-119">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 관리되는 클래스를 사용하여 다양한 작업을 완료하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f0ae0-119">Demonstrates how to complete a variety of tasks using the [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] managed classes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f0ae0-120">참조</span><span class="sxs-lookup"><span data-stu-id="f0ae0-120">Reference</span></span>  
 <xref:System.Drawing>  
 <span data-ttu-id="f0ae0-121">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 기본 그래픽 기능에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ae0-121">Provides access to [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] basic graphics functionality.</span></span>  
  
 <xref:System.Drawing.Drawing2D>  
 <span data-ttu-id="f0ae0-122">고급 2D 및 벡터 그래픽 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ae0-122">Provides advanced two-dimensional and vector graphics functionality.</span></span>  
  
 <xref:System.Drawing.Imaging>  
 <span data-ttu-id="f0ae0-123">고급 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 이미징 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ae0-123">Provides advanced [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] imaging functionality.</span></span>  
  
 <xref:System.Drawing.Text>  
 <span data-ttu-id="f0ae0-124">고급 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 입력 체계 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ae0-124">Provides advanced [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] typography functionality.</span></span> <span data-ttu-id="f0ae0-125">이 네임스페이스의 클래스를 통해 글꼴 컬렉션을 만들고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ae0-125">The classes in this namespace can be used to create and use collections of fonts.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="f0ae0-126">인쇄 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ae0-126">Provides printing functionality.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f0ae0-127">관련 단원</span><span class="sxs-lookup"><span data-stu-id="f0ae0-127">Related Sections</span></span>  
 [<span data-ttu-id="f0ae0-128">사용자 지정 컨트롤 그리기 및 렌더링</span><span class="sxs-lookup"><span data-stu-id="f0ae0-128">Custom Control Painting and Rendering</span></span>](../controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="f0ae0-129">컨트롤을 그리기 위한 코드를 제공하는 방법을 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ae0-129">Details how to provide code for painting controls.</span></span>
