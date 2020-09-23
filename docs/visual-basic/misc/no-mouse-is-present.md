---
title: 마우스가 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrMouse_NoMouseIsPresent
ms.assetid: 4472fd57-4217-4463-9d3c-dc4a8fe88f1b
ms.openlocfilehash: ceb850d98d29c232da304fbdfaddf5611714ef1a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078855"
---
# <a name="no-mouse-is-present"></a><span data-ttu-id="c4c47-102">마우스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c4c47-102">No mouse is present</span></span>

<span data-ttu-id="c4c47-103">`My.Computer.Mouse` 개체의 속성 중 하나를 호출했지만 컴퓨터에 마우스 또는 마우스 포트가 설치되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4c47-103">One of the properties of the `My.Computer.Mouse` object was called, but the computer has no mouse or mouse port installed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c4c47-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="c4c47-104">To correct this error</span></span>  
  
- <span data-ttu-id="c4c47-105">`Try...Catch` 개체의 속성을 호출하는 주변에 `My.Computer.Mouse` 블록을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c4c47-105">Add a `Try...Catch` block around the call to the property of the `My.Computer.Mouse` object.</span></span>  
  
     <span data-ttu-id="c4c47-106">— 또는 —</span><span class="sxs-lookup"><span data-stu-id="c4c47-106">— or —</span></span>  
  
- <span data-ttu-id="c4c47-107">컴퓨터에 마우스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c4c47-107">Install a mouse on the computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4c47-108">참조</span><span class="sxs-lookup"><span data-stu-id="c4c47-108">See also</span></span>

- [<span data-ttu-id="c4c47-109">My.Computer.Mouse</span><span class="sxs-lookup"><span data-stu-id="c4c47-109">My.Computer.Mouse</span></span>](xref:Microsoft.VisualBasic.Devices.Mouse)
- [<span data-ttu-id="c4c47-110">.NET의 예외 처리 및 Throw</span><span class="sxs-lookup"><span data-stu-id="c4c47-110">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="c4c47-111">Try ... Catch ... Finally 문</span><span class="sxs-lookup"><span data-stu-id="c4c47-111">Try...Catch...Finally Statement</span></span>](../language-reference/statements/try-catch-finally-statement.md)
