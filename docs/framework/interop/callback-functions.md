---
title: 콜백 함수
description: 관리되지 않는 DLL 함수가 작업을 완료하는 데 도움이 되는 관리되는 애플리케이션을 사용하는 코드인 콜백 함수에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- callback function
- platform invoke, calling unmanaged functions
ms.assetid: c0aa8533-3b3b-42e8-9f60-84919793098c
ms.openlocfilehash: e28756b5ed935aff83363b38d6f33982e87718b2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621719"
---
# <a name="callback-functions"></a><span data-ttu-id="e589f-103">콜백 함수</span><span class="sxs-lookup"><span data-stu-id="e589f-103">Callback Functions</span></span>
<span data-ttu-id="e589f-104">콜백 함수는 관리되지 않는 DLL 함수가 작업을 완료하는 데 도움이 되는, 관리되는 애플리케이션 내의 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e589f-104">A callback function is code within a managed application that helps an unmanaged DLL function complete a task.</span></span> <span data-ttu-id="e589f-105">콜백 함수 호출은 관리되는 애플리케이션에서 간접적으로, DLL 함수를 통해, 그리고 다시 관리되는 구현으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="e589f-105">Calls to a callback function pass indirectly from a managed application, through a DLL function, and back to the managed implementation.</span></span> <span data-ttu-id="e589f-106">플랫폼 호출을 사용하여 호출되는 많은 DLL 함수 중 일부는 제대로 실행되기 위해 관리 코드에 콜백 함수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e589f-106">Some of the many DLL functions called with platform invoke require a callback function in managed code to run properly.</span></span>  
  
 <span data-ttu-id="e589f-107">관리 코드에서 대부분의 DLL 함수를 호출하려면 관리되는 함수 정의를 만든 후 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e589f-107">To call most DLL functions from managed code, you create a managed definition of the function and then call it.</span></span> <span data-ttu-id="e589f-108">프로세스는 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="e589f-108">The process is straightforward.</span></span>  
  
 <span data-ttu-id="e589f-109">콜백 함수가 필요한 DLL 함수를 사용하는 경우 몇 가지 추가 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e589f-109">Using a DLL function that requires a callback function has some additional steps.</span></span> <span data-ttu-id="e589f-110">먼저, 함수에 대한 설명서를 확인하여 함수에 콜백이 필요한지 여부를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e589f-110">First, you must determine whether the function requires a callback by looking at the documentation for the function.</span></span> <span data-ttu-id="e589f-111">다음으로, 관리되는 애플리케이션에서 콜백 함수를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e589f-111">Next, you have to create the callback function in your managed application.</span></span> <span data-ttu-id="e589f-112">마지막으로, 콜백 함수에 대한 포인터를 인수로 전달하여 DLL 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e589f-112">Finally, you call the DLL function, passing a pointer to the callback function as an argument.</span></span>

 <span data-ttu-id="e589f-113">다음 그림은 콜백 함수 및 구현 단계를 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="e589f-113">The following illustration summarizes the callback function and implementation steps:</span></span>  
  
 ![플랫폼 호출 콜백 프로세스를 보여주는 다이어그램.](./media/callback-functions/platform-invoke-callback-process.gif)  
  
 <span data-ttu-id="e589f-115">콜백 함수는 작업이 반복적으로 수행되는 경우 사용하기에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="e589f-115">Callback functions are ideal for use in situations in which a task is performed repeatedly.</span></span> <span data-ttu-id="e589f-116">또한 일반적으로 Windows API에서 **EnumFontFamilies**, **EnumPrinters**, **EnumWindows** 등의 열거형 함수에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e589f-116">Another common usage is with enumeration functions, such as **EnumFontFamilies**, **EnumPrinters**, and **EnumWindows** in the Windows API.</span></span> <span data-ttu-id="e589f-117">**EnumWindows** 함수는 컴퓨터의 모든 기존 창을 열거하고 콜백 함수를 호출하여 각 창에서 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e589f-117">The **EnumWindows** function enumerates through all existing windows on your computer, calling the callback function to perform a task on each window.</span></span> <span data-ttu-id="e589f-118">자세한 내용과 예제는 [방법: 콜백 함수 구현](how-to-implement-callback-functions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e589f-118">For instructions and an example, see [How to: Implement Callback Functions](how-to-implement-callback-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e589f-119">참조</span><span class="sxs-lookup"><span data-stu-id="e589f-119">See also</span></span>

- [<span data-ttu-id="e589f-120">방법: 콜백 함수 구현</span><span class="sxs-lookup"><span data-stu-id="e589f-120">How to: Implement Callback Functions</span></span>](how-to-implement-callback-functions.md)
- [<span data-ttu-id="e589f-121">DLL 함수 호출</span><span class="sxs-lookup"><span data-stu-id="e589f-121">Calling a DLL Function</span></span>](calling-a-dll-function.md)
