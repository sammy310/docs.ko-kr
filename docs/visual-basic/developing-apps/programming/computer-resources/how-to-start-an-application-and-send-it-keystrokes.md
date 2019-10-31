---
title: '방법: 애플리케이션 시작 및 키 입력 보내기 - Visual Basic'
ms.date: 10/23/2019
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
ms.openlocfilehash: 033999c07bb5839a264122b2ca330916bdf844b8
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919385"
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a><span data-ttu-id="cd6c7-102">방법: 애플리케이션 시작 및 키 입력 보내기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd6c7-102">How to: start an application and send it keystrokes (Visual Basic)</span></span>

<span data-ttu-id="cd6c7-103">이 예제에서는 <xref:Microsoft.VisualBasic.Interaction.Shell%2A> 메서드를 사용하여 메모장 애플리케이션을 시작한 다음, [My.Computer.Keyboard.SendKeys](xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A) 메서드를 통해 키 입력을 보내 문장을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="cd6c7-103">This example uses the <xref:Microsoft.VisualBasic.Interaction.Shell%2A> method to start the Notepad application and then prints a sentence by sending keystrokes using the [My.Computer.Keyboard.SendKeys](xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A) method.</span></span>

## <a name="example"></a><span data-ttu-id="cd6c7-104">예</span><span class="sxs-lookup"><span data-stu-id="cd6c7-104">Example</span></span>

[!code-vb[VbVbalrMyComputer#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#25)]

## <a name="robust-programming"></a><span data-ttu-id="cd6c7-105">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="cd6c7-105">Robust programming</span></span>

<span data-ttu-id="cd6c7-106">요청된 프로세스 식별자를 가진 애플리케이션을 찾을 수 없는 경우 <xref:System.ArgumentException> 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="cd6c7-106">An <xref:System.ArgumentException> exception is raised if an application with the requested process identifier cannot be found.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="cd6c7-107">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="cd6c7-107">.NET Framework Security</span></span>

<span data-ttu-id="cd6c7-108">`Shell` 함수에 대한 호출은 완전 신뢰가 필요합니다(<xref:System.Security.SecurityException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="cd6c7-108">The call to the `Shell` function requires full trust (<xref:System.Security.SecurityException> class).</span></span>

## <a name="see-also"></a><span data-ttu-id="cd6c7-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd6c7-109">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
