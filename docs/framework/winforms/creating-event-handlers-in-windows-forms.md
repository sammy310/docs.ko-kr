---
title: 이벤트 처리기 만들기
description: Windows Forms의 이벤트를 여러 처리기에 할당 하는 방법 및 특정 이벤트를 처리 하는 메서드를 동적으로 변경할 수 있는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- event handling [Windows Forms]
- Windows Forms controls, event handling
- Windows Forms, event handling
- events [Windows Forms], event handlers
- event handlers [Windows Forms]
ms.assetid: 6514e530-c6b8-489c-a8d2-eda7b7072701
ms.openlocfilehash: 4dca198be69c200ea8dfc741a43801bf8f631b9d
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85326009"
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="cbe8c-103">Windows Forms에서 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="cbe8c-103">Creating Event Handlers in Windows Forms</span></span>

<span data-ttu-id="cbe8c-104">이벤트 처리기는 사용자가 단추를 클릭하거나 메시지 큐에서 메시지를 수신하는 등의 이벤트 발생 시 수행되는 작업을 결정하는 코드 내의 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="cbe8c-104">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="cbe8c-105">이벤트가 발생하면 해당 이벤트를 수신하는 하나 이상의 이벤트 처리기가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbe8c-105">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="cbe8c-106">이벤트는 여러 처리기에 할당될 수 있으며 특정 이벤트를 처리하는 메서드가 동적으로 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbe8c-106">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="cbe8c-107">Visual Studio에서 Windows Forms 디자이너를 사용 하 여 이벤트 처리기를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbe8c-107">You can also use the Windows Forms Designer in Visual Studio to create event handlers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="cbe8c-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="cbe8c-108">In This Section</span></span>

 <span data-ttu-id="cbe8c-109">[이벤트 개요](events-overview-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="cbe8c-109">[Events Overview](events-overview-windows-forms.md)</span></span>\
 <span data-ttu-id="cbe8c-110">이벤트 모델과 대리자 역할에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe8c-110">Explains the event model and the role of delegates.</span></span>

 <span data-ttu-id="cbe8c-111">[이벤트 처리기 개요](event-handlers-overview-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="cbe8c-111">[Event Handlers Overview](event-handlers-overview-windows-forms.md)</span></span>\
 <span data-ttu-id="cbe8c-112">이벤트를 처리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe8c-112">Describes how to handle events.</span></span>

 <span data-ttu-id="cbe8c-113">[방법: 런타임에 Windows Forms에 대 한 이벤트 처리기 만들기](how-to-create-event-handlers-at-run-time-for-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="cbe8c-113">[How to: Create Event Handlers at Run Time for Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)</span></span>\
 <span data-ttu-id="cbe8c-114">시스템 또는 사용자 이벤트에 동적으로 응답하는 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe8c-114">Gives directions for responding to system or user events dynamically.</span></span>

 <span data-ttu-id="cbe8c-115">[방법: Windows Forms에서 단일 이벤트 처리기에 여러 이벤트 연결](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="cbe8c-115">[How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)</span></span>\
 <span data-ttu-id="cbe8c-116">이벤트를 통해 여러 컨트롤에 같은 기능을 할당하도록 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe8c-116">Gives directions for assigning the same functionality to multiple controls through events.</span></span>

 <span data-ttu-id="cbe8c-117">[Windows Forms 이벤트 순서](order-of-events-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="cbe8c-117">[Order of Events in Windows Forms](order-of-events-in-windows-forms.md)</span></span>\
 <span data-ttu-id="cbe8c-118">Windows Forms 컨트롤에서 이벤트가 발생하는 순서에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe8c-118">Describes the order in which events are raised in Windows Forms controls.</span></span>

 <span data-ttu-id="cbe8c-119">[방법: 디자이너를 사용 하 여 이벤트 처리기 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Windows Forms 디자이너를 사용 하 여 이벤트 처리기를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe8c-119">[How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Describes how to use the Windows Forms Designer to create event handlers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="cbe8c-120">관련 단원</span><span class="sxs-lookup"><span data-stu-id="cbe8c-120">Related Sections</span></span>

 <span data-ttu-id="cbe8c-121">[이벤트](../../standard/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="cbe8c-121">[Events](../../standard/events/index.md)</span></span>\
 <span data-ttu-id="cbe8c-122">.NET Framework를 사용 하 여 이벤트 처리 및 발생에 대 한 항목의 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe8c-122">Provides links to topics on handling and raising events using the .NET Framework.</span></span>

 <span data-ttu-id="cbe8c-123">[Visual Basic의 상속 된 이벤트 처리기 문제 해결](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)</span><span class="sxs-lookup"><span data-stu-id="cbe8c-123">[Troubleshooting Inherited Event Handlers in Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)</span></span>\
 <span data-ttu-id="cbe8c-124">상속된 구성 요소의 이벤트 처리기에서 발생하는 일반적인 문제에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cbe8c-124">Lists common issues that occur with event handlers in inherited components.</span></span>
