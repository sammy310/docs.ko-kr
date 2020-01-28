---
title: 좌표
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
ms.openlocfilehash: c95888f31bfc867e9c028d53072ab3d710256708
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734670"
---
# <a name="windows-forms-coordinates"></a><span data-ttu-id="da9af-102">Windows Forms 좌표</span><span class="sxs-lookup"><span data-stu-id="da9af-102">Windows Forms Coordinates</span></span>
<span data-ttu-id="da9af-103">Windows Form의 좌표계는 장치 좌표를 기반으로 하며 Windows Forms 그릴 때의 기본 측정 단위는 장치 단위 (일반적으로 픽셀)입니다.</span><span class="sxs-lookup"><span data-stu-id="da9af-103">The coordinate system for a Windows Form is based on device coordinates, and the basic unit of measure when drawing in Windows Forms is the device unit (typically, the pixel).</span></span> <span data-ttu-id="da9af-104">화면의 점은 x 좌표와 y 좌표 쌍으로 표현 되며 x 좌표는 오른쪽으로, y 좌표는 위쪽에서 아래쪽으로 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="da9af-104">Points on the screen are described by x- and y-coordinate pairs, with the x-coordinates increasing to the right and the y-coordinates increasing from top to bottom.</span></span> <span data-ttu-id="da9af-105">화면을 기준으로 하는 원본의 위치는 화면 또는 클라이언트 좌표를 지정 하는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="da9af-105">The location of the origin, relative to the screen, will vary depending on whether you are specifying screen or client coordinates.</span></span>  
  
## <a name="screen-coordinates"></a><span data-ttu-id="da9af-106">화면 좌표</span><span class="sxs-lookup"><span data-stu-id="da9af-106">Screen Coordinates</span></span>  
 <span data-ttu-id="da9af-107">Windows Forms 응용 프로그램 화면 좌표에서 화면에 있는 창의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9af-107">A Windows Forms application specifies the position of a window on the screen in screen coordinates.</span></span> <span data-ttu-id="da9af-108">화면 좌표의 경우 원점은 화면의 왼쪽 위 모퉁이입니다.</span><span class="sxs-lookup"><span data-stu-id="da9af-108">For screen coordinates, the origin is the upper-left corner of the screen.</span></span> <span data-ttu-id="da9af-109">창의 전체 위치는 창의 왼쪽 위 모퉁이와 오른쪽 아래 모퉁이를 정의 하는 두 점의 화면 좌표를 포함 하는 <xref:System.Drawing.Rectangle> 구조로 설명 되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="da9af-109">The full position of a window is often described by a <xref:System.Drawing.Rectangle> structure containing the screen coordinates of two points that define the upper-left and lower-right corners of the window.</span></span>  
  
## <a name="client-coordinates"></a><span data-ttu-id="da9af-110">클라이언트 좌표</span><span class="sxs-lookup"><span data-stu-id="da9af-110">Client Coordinates</span></span>  
 <span data-ttu-id="da9af-111">Windows Forms 응용 프로그램은 폼 이나 컨트롤에서 클라이언트 좌표를 사용 하 여 지점의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9af-111">A Windows Forms application specifies the position of points in a form or control using client coordinates.</span></span> <span data-ttu-id="da9af-112">클라이언트 좌표에 대 한 원본은 컨트롤이 나 폼의 클라이언트 영역에 대 한 왼쪽 위 모퉁이입니다.</span><span class="sxs-lookup"><span data-stu-id="da9af-112">The origin for client coordinates is the upper-left corner of the client area of the control or form.</span></span> <span data-ttu-id="da9af-113">클라이언트 좌표는 화면에 폼 이나 컨트롤의 위치에 관계 없이 응용 프로그램에서 폼 이나 컨트롤을 그릴 때 일관 된 좌표 값을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9af-113">Client coordinates ensure that an application can use consistent coordinate values while drawing in a form or control, regardless of the position of the form or control on the screen.</span></span>  
  
 <span data-ttu-id="da9af-114">클라이언트 영역의 차원은 영역에 대 한 클라이언트 좌표를 포함 하는 <xref:System.Drawing.Rectangle> 구조에도 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da9af-114">The dimensions of the client area are also described by a <xref:System.Drawing.Rectangle> structure that contains client coordinates for the area.</span></span> <span data-ttu-id="da9af-115">모든 경우에서 사각형의 왼쪽 위 좌표는 클라이언트 영역에 포함 되 고, 오른쪽 아래 좌표는 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da9af-115">In all cases, the upper-left coordinate of the rectangle is included in the client area, while the lower-right coordinate is excluded.</span></span> <span data-ttu-id="da9af-116">그래픽 작업에는 클라이언트 영역의 오른쪽 및 아래쪽 가장자리가 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da9af-116">Graphics operations do not include the right and lower edges of a client area.</span></span> <span data-ttu-id="da9af-117">예를 들어 <xref:System.Drawing.Graphics.FillRectangle%2A> 메서드는 지정 된 사각형의 오른쪽 및 아래쪽 가장자리에만 채워지고 이러한 가장자리를 포함 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da9af-117">For example the <xref:System.Drawing.Graphics.FillRectangle%2A> method will fill up to the right and lower edge of the specified rectangle, but will not include these edges.</span></span>  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a><span data-ttu-id="da9af-118">한 좌표 유형에 서 다른 유형으로 매핑</span><span class="sxs-lookup"><span data-stu-id="da9af-118">Mapping From One Type of Coordinate to Another</span></span>  
 <span data-ttu-id="da9af-119">경우에 따라 화면 좌표에서 클라이언트 좌표로 매핑해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da9af-119">Occasionally, you may need to map from screen coordinates to client coordinates.</span></span> <span data-ttu-id="da9af-120"><xref:System.Windows.Forms.Control> 클래스에서 사용할 수 있는 <xref:System.Windows.Forms.Control.PointToClient%2A> 및 <xref:System.Windows.Forms.Control.PointToScreen%2A> 메서드를 사용 하 여이를 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da9af-120">You can easily accomplish this by using the <xref:System.Windows.Forms.Control.PointToClient%2A> and <xref:System.Windows.Forms.Control.PointToScreen%2A> methods available in the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="da9af-121">예를 들어 <xref:System.Windows.Forms.Control>의 <xref:System.Windows.Forms.Control.MousePosition%2A> 속성은 화면 좌표로 보고 되지만 이러한 속성을 클라이언트 좌표로 변환 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="da9af-121">For example, the <xref:System.Windows.Forms.Control.MousePosition%2A> property of <xref:System.Windows.Forms.Control> is reported in screen coordinates, but you may want to convert these to client coordinates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da9af-122">참조</span><span class="sxs-lookup"><span data-stu-id="da9af-122">See also</span></span>

- <xref:System.Windows.Forms.Control.PointToClient%2A>
- <xref:System.Windows.Forms.Control.PointToScreen%2A>
