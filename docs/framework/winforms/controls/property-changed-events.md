---
title: 속성 변경 이벤트
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- properties [Windows Forms], changes
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
ms.openlocfilehash: 0ff5b3874d9de169f4a9f1040d601173af352c06
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703233"
---
# <a name="property-changed-events"></a><span data-ttu-id="d74c4-102">속성 변경 이벤트</span><span class="sxs-lookup"><span data-stu-id="d74c4-102">Property-Changed Events</span></span>
<span data-ttu-id="d74c4-103">명명 된 속성 알림을 보내도록 컨트롤 원하면 *PropertyName* 명명 된 이벤트를 정의 하는 변경 내용을 *PropertyName* `Changed` 라는 이름의 메서드 `On` *PropertyName* `Changed` 는 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="d74c4-103">If you want your control to send notifications when a property named *PropertyName* changes, define an event named *PropertyName*`Changed` and a method named `On`*PropertyName*`Changed` that raises the event.</span></span> <span data-ttu-id="d74c4-104">Windows Forms의 명명 정책을 단어를 추가 하는 것 *Changed* 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d74c4-104">The naming convention in Windows Forms is to append the word *Changed* to the name of the property.</span></span> <span data-ttu-id="d74c4-105">속성 변경 이벤트의 관련된 이벤트 대리자 형식이 <xref:System.EventHandler>, 이벤트 데이터 형식이 <xref:System.EventArgs>합니다.</span><span class="sxs-lookup"><span data-stu-id="d74c4-105">The associated event delegate type for property-changed events is <xref:System.EventHandler>, and the event data type is <xref:System.EventArgs>.</span></span> <span data-ttu-id="d74c4-106">기본 클래스 <xref:System.Windows.Forms.Control> 와 같은 대부분의 속성 변경 이벤트를 정의 <xref:System.Windows.Forms.Control.BackColorChanged>를 <xref:System.Windows.Forms.Control.BackgroundImageChanged>를 <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>, 등입니다.</span><span class="sxs-lookup"><span data-stu-id="d74c4-106">The base class <xref:System.Windows.Forms.Control> defines many property-changed events, such as <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>, and others.</span></span> <span data-ttu-id="d74c4-107">이벤트에 대 한 배경 정보를 참조 하세요 [이벤트](../../../standard/events/index.md) 하 고 [Windows Forms 컨트롤의 이벤트](events-in-windows-forms-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d74c4-107">For background information about events, see [Events](../../../standard/events/index.md) and [Events in Windows Forms Controls](events-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="d74c4-108">속성 변경 이벤트 소비자 컨트롤의 변경에 응답 하는 이벤트 처리기를 연결할 수 있도록 하므로 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d74c4-108">Property-changed events are useful because they allow consumers of a control to attach event handlers that respond to the change.</span></span> <span data-ttu-id="d74c4-109">컨트롤을 발생 시킨 속성 변경 이벤트에 응답 하는 경우 해당 재정의 `On` *PropertyName* `Changed` 이벤트에 대리자를 연결 하는 대신 메서드.</span><span class="sxs-lookup"><span data-stu-id="d74c4-109">If your control needs to respond to a property-changed event that it raises, override the corresponding `On`*PropertyName*`Changed` method instead of attaching a delegate to the event.</span></span> <span data-ttu-id="d74c4-110">일반적으로 컨트롤을 다른 속성을 업데이트 하거나 일부 또는 모든 그리기 화면을 그려서 속성 변경 이벤트에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="d74c4-110">A control typically responds to a property-changed event by updating other properties or by redrawing some or all of its drawing surface.</span></span>  
  
 <span data-ttu-id="d74c4-111">다음 예제와 방법을 `FlashTrackBar` 사용자 지정 컨트롤에서 상속 하는 속성 변경 이벤트의 일부에 대 한 응답 <xref:System.Windows.Forms.Control>합니다.</span><span class="sxs-lookup"><span data-stu-id="d74c4-111">The following example shows how the `FlashTrackBar` custom control responds to some of the property-changed events that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="d74c4-112">전체 샘플을 참조 하세요. [방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기](how-to-create-a-windows-forms-control-that-shows-progress.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d74c4-112">For the complete sample, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d74c4-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="d74c4-113">See also</span></span>
- [<span data-ttu-id="d74c4-114">이벤트</span><span class="sxs-lookup"><span data-stu-id="d74c4-114">Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="d74c4-115">Windows Forms 컨트롤의 이벤트</span><span class="sxs-lookup"><span data-stu-id="d74c4-115">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="d74c4-116">Windows Forms 컨트롤의 속성</span><span class="sxs-lookup"><span data-stu-id="d74c4-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
