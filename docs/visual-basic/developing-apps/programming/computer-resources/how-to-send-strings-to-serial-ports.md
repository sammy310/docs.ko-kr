---
description: '자세한 정보: 방법: Visual Basic에서 직렬 포트로 문자열 보내기'
title: '방법: 직렬 포트로 문자열 보내기'
ms.date: 07/20/2015
helpviewer_keywords:
- ports, sending strings to
- strings [Visual Basic], sending to serial ports
- My.Computer.Ports object
- serial ports, sending strings to
ms.assetid: 6ebf46cd-b2d0-4b2c-9a1f-be177b22ad52
ms.openlocfilehash: 66dedaab05090af2659701e57b37b4813447b8ef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666487"
---
# <a name="how-to-send-strings-to-serial-ports-in-visual-basic"></a><span data-ttu-id="07c75-103">방법: Visual Basic에서 직렬 포트로 문자열 보내기</span><span class="sxs-lookup"><span data-stu-id="07c75-103">How to: Send Strings to Serial Ports in Visual Basic</span></span>

<span data-ttu-id="07c75-104">이 항목에서는 Visual Basic에서 `My.Computer.Ports`를 사용하여 컴퓨터의 직렬 포트에 문자열을 보내는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="07c75-104">This topic describes how to use `My.Computer.Ports` to send strings to the computer's serial ports in Visual Basic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07c75-105">예제</span><span class="sxs-lookup"><span data-stu-id="07c75-105">Example</span></span>  

 <span data-ttu-id="07c75-106">이 예제에서는 COM1 직렬 포트에 문자열을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="07c75-106">This example sends a string to the COM1 serial port.</span></span> <span data-ttu-id="07c75-107">컴퓨터의 다른 직렬 포트를 사용해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c75-107">You may need to use a different serial port on your computer.</span></span>  
  
 <span data-ttu-id="07c75-108">`My.Computer.Ports.OpenSerialPort` 메서드를 사용하여 포트에 대한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="07c75-108">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="07c75-109">자세한 내용은 <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07c75-109">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
 <span data-ttu-id="07c75-110">`Using` 블록을 사용하면 예외를 생성하는 경우 애플리케이션이 직렬 포트를 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c75-110">The `Using` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="07c75-111">직렬 포트를 조작하는 모든 코드는 이 블록 안이나 `Try...Catch...Finally` 블록 안에 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c75-111">All code that manipulates the serial port should appear within this block or within a `Try...Catch...Finally` block.</span></span>  
  
 <span data-ttu-id="07c75-112"><xref:System.IO.Ports.SerialPort.WriteLine%2A> 메서드는 데이터를 직렬 포트로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="07c75-112">The <xref:System.IO.Ports.SerialPort.WriteLine%2A> method sends the data to the serial port.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#33)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="07c75-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="07c75-113">Compiling the Code</span></span>  
  
- <span data-ttu-id="07c75-114">이 예제에서는 컴퓨터가 `COM1`을 사용 중이라고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="07c75-114">This example assumes the computer is using `COM1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="07c75-115">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="07c75-115">Robust Programming</span></span>  

 <span data-ttu-id="07c75-116">이 예제에서는 컴퓨터가 `COM1`을 사용 중이라고 가정합니다. 유연성 향상을 위해 코드에서 사용자가 사용 가능한 포트 목록에서 원하는 직렬 포트를 선택할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c75-116">This example assumes the computer is using `COM1`; for more flexibility, the code should allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="07c75-117">자세한 내용은 [방법: 사용할 수 있는 직렬 포트 표시](how-to-show-available-serial-ports.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07c75-117">For more information, see [How to: Show Available Serial Ports](how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="07c75-118">이 예제에서는 `Using` 블록을 사용하여 예외가 throw되는 경우에도 애플리케이션이 포트를 닫도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c75-118">This example uses a `Using` block to make sure that the application closes the port even if it throws an exception.</span></span> <span data-ttu-id="07c75-119">자세한 내용은 [using 문](../../../language-reference/statements/using-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07c75-119">For more information, see [Using Statement](../../../language-reference/statements/using-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07c75-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07c75-120">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [<span data-ttu-id="07c75-121">방법: 직렬 포트에 연결된 모뎀 전화 접속</span><span class="sxs-lookup"><span data-stu-id="07c75-121">How to: Dial Modems Attached to Serial Ports</span></span>](how-to-dial-modems-attached-to-serial-ports.md)
- [<span data-ttu-id="07c75-122">방법: 사용 가능한 직렬 포트 표시</span><span class="sxs-lookup"><span data-stu-id="07c75-122">How to: Show Available Serial Ports</span></span>](how-to-show-available-serial-ports.md)
