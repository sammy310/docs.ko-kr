---
title: Windows Forms 좌표
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
ms.openlocfilehash: 6feabadff17538f4a7368c348f7b72226e2d678e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116141"
---
# <a name="windows-forms-coordinates"></a><span data-ttu-id="adc53-102">Windows Forms 좌표</span><span class="sxs-lookup"><span data-stu-id="adc53-102">Windows Forms Coordinates</span></span>
<span data-ttu-id="adc53-103">Windows 폼을 위한 좌표계 장치 좌표를 기준으로 하며 Windows Forms에서 그릴 때의 기본 단위는 장치 단위 (일반적으로 픽셀)입니다.</span><span class="sxs-lookup"><span data-stu-id="adc53-103">The coordinate system for a Windows Form is based on device coordinates, and the basic unit of measure when drawing in Windows Forms is the device unit (typically, the pixel).</span></span> <span data-ttu-id="adc53-104">지점은 화면에서 오른쪽, 위쪽에서 아래쪽 증가 y 좌표를 증가 하는 x 좌표를 사용 하 여 x 및 y 좌표 쌍에 의해 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adc53-104">Points on the screen are described by x- and y-coordinate pairs, with the x-coordinates increasing to the right and the y-coordinates increasing from top to bottom.</span></span> <span data-ttu-id="adc53-105">화면을 기준으로 원본 위치의 클라이언트 또는 화면 좌표를 지정 하는 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="adc53-105">The location of the origin, relative to the screen, will vary depending on whether you are specifying screen or client coordinates.</span></span>  
  
## <a name="screen-coordinates"></a><span data-ttu-id="adc53-106">화면 좌표</span><span class="sxs-lookup"><span data-stu-id="adc53-106">Screen Coordinates</span></span>  
 <span data-ttu-id="adc53-107">Windows Forms 응용 프로그램을 화면 좌표에서 화면에서 창의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc53-107">A Windows Forms application specifies the position of a window on the screen in screen coordinates.</span></span> <span data-ttu-id="adc53-108">화면 좌표에 대 한 원점은 화면의 왼쪽 위 모퉁이입니다.</span><span class="sxs-lookup"><span data-stu-id="adc53-108">For screen coordinates, the origin is the upper-left corner of the screen.</span></span> <span data-ttu-id="adc53-109">창의 전체 위치에서 설명한 종종는 <xref:System.Drawing.Rectangle> 창의 왼쪽 및 오른쪽 아래 모퉁이 정의 하는 두 지점의 화면 좌표를 포함 하는 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="adc53-109">The full position of a window is often described by a <xref:System.Drawing.Rectangle> structure containing the screen coordinates of two points that define the upper-left and lower-right corners of the window.</span></span>  
  
## <a name="client-coordinates"></a><span data-ttu-id="adc53-110">클라이언트 좌표</span><span class="sxs-lookup"><span data-stu-id="adc53-110">Client Coordinates</span></span>  
 <span data-ttu-id="adc53-111">Windows Forms 응용 프로그램을 폼 이나 클라이언트 좌표를 사용 하 여 컨트롤에서 점의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc53-111">A Windows Forms application specifies the position of points in a form or control using client coordinates.</span></span> <span data-ttu-id="adc53-112">클라이언트 좌표에 대 한 원본은 컨트롤이 나 폼의 클라이언트 영역의 왼쪽 위 모퉁이.</span><span class="sxs-lookup"><span data-stu-id="adc53-112">The origin for client coordinates is the upper-left corner of the client area of the control or form.</span></span> <span data-ttu-id="adc53-113">클라이언트 좌표로 응용 프로그램 폼 또는 폼 또는 화면에서 컨트롤의 위치에 관계 없이 컨트롤에서 그리기 하는 동안 일관 된 좌표 값을 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc53-113">Client coordinates ensure that an application can use consistent coordinate values while drawing in a form or control, regardless of the position of the form or control on the screen.</span></span>  
  
 <span data-ttu-id="adc53-114">클라이언트 영역의 크기에 대해서도 설명 하 여는 <xref:System.Drawing.Rectangle> 영역에 대 한 클라이언트 좌표를 포함 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="adc53-114">The dimensions of the client area are also described by a <xref:System.Drawing.Rectangle> structure that contains client coordinates for the area.</span></span> <span data-ttu-id="adc53-115">모든 경우에 사각형의 왼쪽 위 좌표는 오른쪽 아래 좌표는 제외 하는 동안 클라이언트 영역에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adc53-115">In all cases, the upper-left coordinate of the rectangle is included in the client area, while the lower-right coordinate is excluded.</span></span> <span data-ttu-id="adc53-116">그래픽 작업을 클라이언트 영역 오른쪽 및 아래쪽 가장자리를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="adc53-116">Graphics operations do not include the right and lower edges of a client area.</span></span> <span data-ttu-id="adc53-117">예를 들어를 <xref:System.Drawing.Graphics.FillRectangle%2A> 메서드는 지정 된 사각형의 오른쪽 및 아래쪽 가장자리에 꽉 차게 됩니다 있지만 이러한 가장자리를 포함 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="adc53-117">For example the <xref:System.Drawing.Graphics.FillRectangle%2A> method will fill up to the right and lower edge of the specified rectangle, but will not include these edges.</span></span>  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a><span data-ttu-id="adc53-118">다른 한 가지 유형의 좌표에서 매핑</span><span class="sxs-lookup"><span data-stu-id="adc53-118">Mapping From One Type of Coordinate to Another</span></span>  
 <span data-ttu-id="adc53-119">경우에 따라 클라이언트 좌표를 화면 좌표에서 지도를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adc53-119">Occasionally, you may need to map from screen coordinates to client coordinates.</span></span> <span data-ttu-id="adc53-120">사용 하 여 쉽게 수행할 수 있습니다 합니다 <xref:System.Windows.Forms.Control.PointToClient%2A> 및 <xref:System.Windows.Forms.Control.PointToScreen%2A> 에서 사용할 수 있는 메서드는 <xref:System.Windows.Forms.Control> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="adc53-120">You can easily accomplish this by using the <xref:System.Windows.Forms.Control.PointToClient%2A> and <xref:System.Windows.Forms.Control.PointToScreen%2A> methods available in the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="adc53-121">예를 들어를 <xref:System.Windows.Forms.Control.MousePosition%2A> 의 속성 <xref:System.Windows.Forms.Control> 화면 좌표에서 보고 되는 클라이언트 좌표로 변환할 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adc53-121">For example, the <xref:System.Windows.Forms.Control.MousePosition%2A> property of <xref:System.Windows.Forms.Control> is reported in screen coordinates, but you may want to convert these to client coordinates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adc53-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="adc53-122">See also</span></span>

- <xref:System.Windows.Forms.Control.PointToClient%2A>
- <xref:System.Windows.Forms.Control.PointToScreen%2A>
