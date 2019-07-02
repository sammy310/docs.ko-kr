---
title: 그래픽 개요
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: f0e2fd9dcf31e5fdce16b5a3b6fd21eab6eab66a
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505327"
---
# <a name="overview-of-graphics"></a><span data-ttu-id="29bba-102">그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="29bba-102">Overview of Graphics</span></span>
<span data-ttu-id="29bba-103">GDI +는 API (응용 프로그래밍 인터페이스)는 Microsoft Windows 운영 체제의 하위 시스템을 구성 하는 경우</span><span class="sxs-lookup"><span data-stu-id="29bba-103">GDI+ is an application programming interface (API) that forms the subsystem of the Microsoft Windows operating system.</span></span> <span data-ttu-id="29bba-104">GDI +는 화면과 프린터에 정보를 표시 하는 일을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="29bba-104">GDI+ is responsible for displaying information on screens and printers.</span></span> <span data-ttu-id="29bba-105">해당 이름에서 알 수 있듯이, GDI +는 GDI, 이전 버전의 Windows에 포함 된 그래픽 장치 인터페이스에 대 한 후속입니다.</span><span class="sxs-lookup"><span data-stu-id="29bba-105">As its name suggests, GDI+ is the successor to GDI, the Graphics Device Interface included with earlier versions of Windows.</span></span>  
  
## <a name="managed-class-interface"></a><span data-ttu-id="29bba-106">관리되는 클래스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="29bba-106">Managed Class Interface</span></span>  
 <span data-ttu-id="29bba-107">GDI + API는 관리 코드로 배포 된 클래스 집합을 통해 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29bba-107">The GDI+ API is exposed through a set of classes deployed as managed code.</span></span> <span data-ttu-id="29bba-108">이 클래스 집합을 이라고 합니다 *관리 되는 클래스 인터페이스* GDI +입니다.</span><span class="sxs-lookup"><span data-stu-id="29bba-108">This set of classes is called the *managed class interface* to GDI+.</span></span> <span data-ttu-id="29bba-109">다음 네임스페이스는 관리되는 클래스 인터페이스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="29bba-109">The following namespaces make up the managed class interface:</span></span>  
  
- <xref:System.Drawing>  
  
- <xref:System.Drawing.Drawing2D>  
  
- <xref:System.Drawing.Imaging>  
  
- <xref:System.Drawing.Text>  
  
- <xref:System.Drawing.Printing>  
  
 <span data-ttu-id="29bba-110">GDI +에서 같은 그래픽 장치 인터페이스를 사용 하 여 특정 디스플레이 장치의 세부 정보를 염려 하지 않고 화면 또는 프린터에 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29bba-110">With a Graphics Device Interface, such as GDI+, you can display information on a screen or printer without having to be concerned about the details of a particular display device.</span></span> <span data-ttu-id="29bba-111">프로그래머가 GDI + 클래스에서 제공 하는 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="29bba-111">The programmer makes calls to methods provided by GDI+ classes.</span></span> <span data-ttu-id="29bba-112">이러한 메서드가 다시 특정 장치 드라이버에 대한 적절한 호출을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="29bba-112">Those methods, in turn, make the appropriate calls to specific device drivers.</span></span> <span data-ttu-id="29bba-113">GDI + 그래픽 하드웨어에서 응용 프로그램을 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="29bba-113">GDI+ insulates the application from the graphics hardware.</span></span> <span data-ttu-id="29bba-114">이 프로그래머가 장치 독립적인 응용 프로그램을 만들 수는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="29bba-114">It is this insulation that enables a programmer to create device-independent applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29bba-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="29bba-115">See also</span></span>

- [<span data-ttu-id="29bba-116">그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="29bba-116">Graphics Overview</span></span>](graphics-overview-windows-forms.md)
