---
title: 그래픽 및 그리기
description: 그래픽, 펜, 브러시 및 색 개체에 대해 알아보고, 도형을 그리거나, 텍스트를 그리거나, Windows Forms에서 이미지를 표시 하는 등의 작업을 수행 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 58d8cde6aa102225cf9e3c342efe37218c818307
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618404"
---
# <a name="graphics-and-drawing-in-windows-forms"></a><span data-ttu-id="393f4-103">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="393f4-103">Graphics and Drawing in Windows Forms</span></span>
<span data-ttu-id="393f4-104">공용 언어 런타임은 gdi + 라는 Windows GDI (그래픽 장치 인터페이스)의 고급 구현을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="393f4-104">The common language runtime uses an advanced implementation of the Windows Graphics Device Interface (GDI) called GDI+.</span></span> <span data-ttu-id="393f4-105">GDI +를 사용 하 여 그래픽을 만들고, 텍스트를 그리고, 그래픽 이미지를 개체로 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393f4-105">With GDI+ you can create graphics, draw text, and manipulate graphical images as objects.</span></span> <span data-ttu-id="393f4-106">GDI +는 성능과 사용 편의성을 제공 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="393f4-106">GDI+ is designed to offer performance and ease of use.</span></span> <span data-ttu-id="393f4-107">GDI +를 사용 하 여 Windows Forms 및 컨트롤에 그래픽 이미지를 렌더링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393f4-107">You can use GDI+ to render graphical images on Windows Forms and controls.</span></span> <span data-ttu-id="393f4-108">Web Forms에서 GDI +를 직접 사용할 수는 없지만 이미지 웹 서버 컨트롤을 통해 그래픽 이미지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393f4-108">Although you cannot use GDI+ directly on Web Forms, you can display graphical images through the Image Web Server control.</span></span>  
  
 <span data-ttu-id="393f4-109">이 섹션에서는 GDI + 프로그래밍의 기본 사항을 소개 하는 항목을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393f4-109">In this section, you will find topics that introduce the fundamentals of GDI+ programming.</span></span> <span data-ttu-id="393f4-110">포괄적인 참조는 아니지만 이 섹션은 <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> 및 <xref:System.Drawing.Color> 개체에 대한 정보를 포함하며 도형 그리기, 텍스트 그리기 또는 이미지 표시와 같은 작업을 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="393f4-110">Although not intended to be a comprehensive reference, this section includes information about the <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, and <xref:System.Drawing.Color> objects, and explains how to perform such tasks as drawing shapes, drawing text, or displaying images.</span></span> <span data-ttu-id="393f4-111">자세한 내용은 [Gdi + 참조](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="393f4-111">For more information, see [GDI+ Reference](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span></span>  
  
 <span data-ttu-id="393f4-112">바로 시작하려면 [그래픽 프로그래밍 시작](getting-started-with-graphics-programming.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="393f4-112">If you'd like to jump in and get started right away, see [Getting Started with Graphics Programming](getting-started-with-graphics-programming.md).</span></span> <span data-ttu-id="393f4-113">Windows Forms에서 코드를 사용하여 선, 도형, 텍스트 등을 그리는 방법에 대한 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393f4-113">It has topics on how to use code to draw lines, shapes, text, and more on Windows forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="393f4-114">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="393f4-114">In This Section</span></span>  
 [<span data-ttu-id="393f4-115">그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="393f4-115">Graphics Overview</span></span>](graphics-overview-windows-forms.md)  
 <span data-ttu-id="393f4-116">그래픽 관련 관리되는 클래스를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="393f4-116">Provides an introduction to the graphics-related managed classes.</span></span>  
  
 [<span data-ttu-id="393f4-117">GDI+ 관리 코드 정보</span><span class="sxs-lookup"><span data-stu-id="393f4-117">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
 <span data-ttu-id="393f4-118">관리 GDI + 클래스에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="393f4-118">Provides information about the managed GDI+ classes.</span></span>  
  
 [<span data-ttu-id="393f4-119">관리형 그래픽 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="393f4-119">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)  
 <span data-ttu-id="393f4-120">GDI + 관리 되는 클래스를 사용 하 여 다양 한 작업을 완료 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="393f4-120">Demonstrates how to complete a variety of tasks using the GDI+ managed classes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="393f4-121">참조</span><span class="sxs-lookup"><span data-stu-id="393f4-121">Reference</span></span>  
 <xref:System.Drawing>  
 <span data-ttu-id="393f4-122">GDI + 기본 그래픽 기능에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="393f4-122">Provides access to GDI+ basic graphics functionality.</span></span>  
  
 <xref:System.Drawing.Drawing2D>  
 <span data-ttu-id="393f4-123">고급 2D 및 벡터 그래픽 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="393f4-123">Provides advanced two-dimensional and vector graphics functionality.</span></span>  
  
 <xref:System.Drawing.Imaging>  
 <span data-ttu-id="393f4-124">고급 GDI + 이미징 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="393f4-124">Provides advanced GDI+ imaging functionality.</span></span>  
  
 <xref:System.Drawing.Text>  
 <span data-ttu-id="393f4-125">고급 GDI + 입력 체계 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="393f4-125">Provides advanced GDI+ typography functionality.</span></span> <span data-ttu-id="393f4-126">이 네임스페이스의 클래스를 통해 글꼴 컬렉션을 만들고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="393f4-126">The classes in this namespace can be used to create and use collections of fonts.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="393f4-127">인쇄 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="393f4-127">Provides printing functionality.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="393f4-128">관련 단원</span><span class="sxs-lookup"><span data-stu-id="393f4-128">Related Sections</span></span>  
 [<span data-ttu-id="393f4-129">사용자 지정 컨트롤 그리기 및 렌더링</span><span class="sxs-lookup"><span data-stu-id="393f4-129">Custom Control Painting and Rendering</span></span>](../controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="393f4-130">컨트롤을 그리기 위한 코드를 제공하는 방법을 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="393f4-130">Details how to provide code for painting controls.</span></span>
