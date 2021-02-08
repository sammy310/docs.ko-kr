---
description: '자세한 정보: Cordebug인터페이스 버전 열거'
title: CorDebugInterfaceVersion 열거형
ms.date: 03/30/2017
api_name:
- CorDebugInterfaceVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInterfaceVersion
helpviewer_keywords:
- CorDebugInterfaceVersion enumeration [.NET Framework debugging]
ms.assetid: 7d1e6cd9-2a15-41c6-9b68-008705a4ed90
topic_type:
- apiref
ms.openlocfilehash: 35b8fd6eae2b7999d7669632506cfea43dffbd45
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801646"
---
# <a name="cordebuginterfaceversion-enumeration"></a><span data-ttu-id="36d8e-103">CorDebugInterfaceVersion 열거형</span><span class="sxs-lookup"><span data-stu-id="36d8e-103">CorDebugInterfaceVersion Enumeration</span></span>

<span data-ttu-id="36d8e-104">인터페이스, 특정 .NET Framework 버전 또는 인터페이스가 적용된 .NET Framework 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="36d8e-104">Specifies an interface, a version of the .NET Framework, or a version of the .NET Framework in which an interface was introduced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36d8e-105">구문</span><span class="sxs-lookup"><span data-stu-id="36d8e-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugInterfaceVersion {  
  
    CorDebugInvalidVersion            = 0,  
    CorDebugVersion_1_0               = CorDebugInvalidVersion + 1,  
  
    ver_ICorDebugManagedCallback      = CorDebugVersion_1_0,  
    ver_ICorDebugUnmanagedCallback    = CorDebugVersion_1_0,  
    ver_ICorDebug                     = CorDebugVersion_1_0,  
    ver_ICorDebugController           = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomain            = CorDebugVersion_1_0,  
    ver_ICorDebugAssembly             = CorDebugVersion_1_0,  
    ver_ICorDebugProcess              = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpoint           = CorDebugVersion_1_0,  
    ver_ICorDebugFunctionBreakpoint   = CorDebugVersion_1_0,  
    ver_ICorDebugModuleBreakpoint     = CorDebugVersion_1_0,  
    ver_ICorDebugValueBreakpoint      = CorDebugVersion_1_0,  
    ver_ICorDebugStepper              = CorDebugVersion_1_0,  
    ver_ICorDebugRegisterSet          = CorDebugVersion_1_0,  
    ver_ICorDebugThread               = CorDebugVersion_1_0,  
    ver_ICorDebugChain                = CorDebugVersion_1_0,  
    ver_ICorDebugFrame                = CorDebugVersion_1_0,  
    ver_ICorDebugILFrame              = CorDebugVersion_1_0,  
    ver_ICorDebugNativeFrame          = CorDebugVersion_1_0,  
    ver_ICorDebugModule               = CorDebugVersion_1_0,  
    ver_ICorDebugFunction             = CorDebugVersion_1_0,  
    ver_ICorDebugCode                 = CorDebugVersion_1_0,  
    ver_ICorDebugClass                = CorDebugVersion_1_0,  
    ver_ICorDebugEval                 = CorDebugVersion_1_0,  
    ver_ICorDebugValue                = CorDebugVersion_1_0,  
    ver_ICorDebugGenericValue         = CorDebugVersion_1_0,  
    ver_ICorDebugReferenceValue       = CorDebugVersion_1_0,  
    ver_ICorDebugHeapValue            = CorDebugVersion_1_0,  
    ver_ICorDebugObjectValue          = CorDebugVersion_1_0,  
    ver_ICorDebugBoxValue             = CorDebugVersion_1_0,  
    ver_ICorDebugStringValue          = CorDebugVersion_1_0,  
    ver_ICorDebugArrayValue           = CorDebugVersion_1_0,  
    ver_ICorDebugContext              = CorDebugVersion_1_0,  
    ver_ICorDebugEnum                 = CorDebugVersion_1_0,  
    ver_ICorDebugObjectEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpointEnum       = CorDebugVersion_1_0,  
    ver_ICorDebugStepperEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugProcessEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugThreadEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugFrameEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugChainEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugModuleEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugValueEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugCodeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugTypeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugErrorInfoEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomainEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAssemblyEnum         = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueErrorInfo
                                      = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueSnapshot
                                      = CorDebugVersion_1_0,  
  
    CorDebugVersion_1_1               = CorDebugVersion_1_0 + 1,  
    // No interface definitions in version 1.1.  
  
    CorDebugVersion_2_0 = CorDebugVersion_1_1 + 1,  
  
    ver_ICorDebugManagedCallback2    = CorDebugVersion_2_0,  
    ver_ICorDebugAppDomain2          = CorDebugVersion_2_0,  
    ver_ICorDebugProcess2            = CorDebugVersion_2_0,  
    ver_ICorDebugStepper2            = CorDebugVersion_2_0,  
    ver_ICorDebugRegisterSet2        = CorDebugVersion_2_0,  
    ver_ICorDebugThread2             = CorDebugVersion_2_0,  
    ver_ICorDebugILFrame2            = CorDebugVersion_2_0,  
    ver_ICorDebugModule2             = CorDebugVersion_2_0,  
    ver_ICorDebugFunction2           = CorDebugVersion_2_0,  
    ver_ICorDebugCode2               = CorDebugVersion_2_0,  
    ver_ICorDebugClass2              = CorDebugVersion_2_0,  
    ver_ICorDebugValue2              = CorDebugVersion_2_0,  
    ver_ICorDebugEval2               = CorDebugVersion_2_0,  
    ver_ICorDebugObjectValue2        = CorDebugVersion_2_0,  
  
    // CLR v4 - next major CLR version after CLR v2  
    // Includes Silverlight 4  
    CorDebugVersion_4_0 = CorDebugVersion_2_0 + 1,  
  
    ver_ICorDebugThread3             = CorDebugVersion_4_0,  
    ver_ICorDebugThread4             = CorDebugVersion_4_0,  
    ver_ICorDebugStackWalk           = CorDebugVersion_4_0,  
    ver_ICorDebugNativeFrame2        = CorDebugVersion_4_0,  
    ver_ICorDebugInternalFrame2      = CorDebugVersion_4_0,  
    ver_ICorDebugRuntimeUnwindableFrame = CorDebugVersion_4_0,  
    ver_ICorDebugHeapValue3          = CorDebugVersion_4_0,  
    ver_ICorDebugBlockingObjectEnum  = CorDebugVersion_4_0,  
    ver_ICorDebugValue3 = CorDebugVersion_4_0,  
  
    CorDebugVersion_4_5 = CorDebugVersion_4_0 + 1,  
  
    ver_ICorDebugComObjectValue = CorDebugVersion_4_5,  
    ver_ICorDebugAppDomain3 = CorDebugVersion_4_5,  
    ver_ICorDebugCode3 = CorDebugVersion_4_5,  
    ver_ICorDebugILFrame3 = CorDebugVersion_4_5,  
  
    CorDebugLatestVersion = CorDebugVersion_4_5  
  
} CorDebugInterfaceVersion;  
```  
  
## <a name="members"></a><span data-ttu-id="36d8e-106">구성원</span><span class="sxs-lookup"><span data-stu-id="36d8e-106">Members</span></span>  

 <span data-ttu-id="36d8e-107">다음 테이블에는 각 열거형 값에서 해당 인터페이스의 링크와</span><span class="sxs-lookup"><span data-stu-id="36d8e-107">The following table provides links from each enumeration value to the corresponding interface.</span></span> <span data-ttu-id="36d8e-108">인터페이스가 지원되는 첫 번째.NET Framework 버전이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36d8e-108">In addition, the table indicates the first version of the .NET Framework that the interface was supported in.</span></span>  
  
|<span data-ttu-id="36d8e-109">멤버</span><span class="sxs-lookup"><span data-stu-id="36d8e-109">Member</span></span>|<span data-ttu-id="36d8e-110">설명</span><span class="sxs-lookup"><span data-stu-id="36d8e-110">Specifies</span></span>|<span data-ttu-id="36d8e-111">.NET Framework 버전</span><span class="sxs-lookup"><span data-stu-id="36d8e-111">.NET Framework version</span></span>|  
|------------|---------------|----------------------------|  
|`CorDebugInvalidVersion`|<span data-ttu-id="36d8e-112">.NET Framework 버전이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="36d8e-112">The version of the .NET Framework is invalid.</span></span>|-|  
|`CorDebugVersion_1_0`|<span data-ttu-id="36d8e-113">모든 서비스 팩을 포함한 .NET Framework 버전이 1.0입니다.</span><span class="sxs-lookup"><span data-stu-id="36d8e-113">The version of the .NET Framework, including all its service packs, is 1.0.</span></span>|<span data-ttu-id="36d8e-114">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-114">1.0</span></span>|  
|`CorDebugVersion_1_1`|<span data-ttu-id="36d8e-115">모든 서비스 팩을 포함한 .NET Framework 버전이 1.1입니다.</span><span class="sxs-lookup"><span data-stu-id="36d8e-115">The version of the .NET Framework, including all service packs, is 1.1.</span></span>|<span data-ttu-id="36d8e-116">1.1</span><span class="sxs-lookup"><span data-stu-id="36d8e-116">1.1</span></span>|  
|`CorDebugVersion_2_0`|<span data-ttu-id="36d8e-117">모든 서비스 팩을 포함한 .NET Framework 버전이 2.0입니다.</span><span class="sxs-lookup"><span data-stu-id="36d8e-117">The version of the .NET Framework, including all service packs, is 2.0.</span></span>|<span data-ttu-id="36d8e-118">2.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-118">2.0</span></span>|  
|`CorDebugVersion_4_0`|<span data-ttu-id="36d8e-119">모든 서비스 팩을 포함한 .NET Framework 버전이 4입니다.</span><span class="sxs-lookup"><span data-stu-id="36d8e-119">The version of the .NET Framework, including all service packs, is 4.</span></span>|<span data-ttu-id="36d8e-120">4</span><span class="sxs-lookup"><span data-stu-id="36d8e-120">4</span></span>|  
|`CorDebugVersion_4_5`|<span data-ttu-id="36d8e-121">모든 서비스 팩을 포함한 .NET Framework 버전이 4.5입니다.</span><span class="sxs-lookup"><span data-stu-id="36d8e-121">The version of the .NET Framework, including all service packs, is 4.5.</span></span>|<span data-ttu-id="36d8e-122">4.5.</span><span class="sxs-lookup"><span data-stu-id="36d8e-122">4.5</span></span>|  
|`ver_ICorDebugManagedCallback`|[<span data-ttu-id="36d8e-123">ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="36d8e-123">ICorDebugManagedCallback</span></span>](icordebugmanagedcallback-interface.md)|<span data-ttu-id="36d8e-124">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-124">1.0</span></span>|  
|`ver_ICorDebugUnmanagedCallback`|[<span data-ttu-id="36d8e-125">ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="36d8e-125">ICorDebugUnmanagedCallback</span></span>](icordebugunmanagedcallback-interface.md)|<span data-ttu-id="36d8e-126">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-126">1.0</span></span>|  
|`ver_ICorDebug`|[<span data-ttu-id="36d8e-127">ICorDebug</span><span class="sxs-lookup"><span data-stu-id="36d8e-127">ICorDebug</span></span>](icordebug-interface.md)|<span data-ttu-id="36d8e-128">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-128">1.0</span></span>|  
|`ver_ICorDebugController`|[<span data-ttu-id="36d8e-129">ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="36d8e-129">ICorDebugController</span></span>](icordebugcontroller-interface.md)|<span data-ttu-id="36d8e-130">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-130">1.0</span></span>|  
|`ver_ICorDebugAppDomain`|[<span data-ttu-id="36d8e-131">ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="36d8e-131">ICorDebugAppDomain</span></span>](icordebugappdomain-interface.md)|<span data-ttu-id="36d8e-132">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-132">1.0</span></span>|  
|`ver_ICorDebugAssembly`|[<span data-ttu-id="36d8e-133">ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="36d8e-133">ICorDebugAssembly</span></span>](icordebugassembly-interface.md)|<span data-ttu-id="36d8e-134">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-134">1.0</span></span>|  
|`ver_ICorDebugProcess`|[<span data-ttu-id="36d8e-135">ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="36d8e-135">ICorDebugProcess</span></span>](icordebugprocess-interface.md)|<span data-ttu-id="36d8e-136">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-136">1.0</span></span>|  
|`ver_ICorDebugBreakpoint`|[<span data-ttu-id="36d8e-137">ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="36d8e-137">ICorDebugBreakpoint</span></span>](icordebugbreakpoint-interface.md)|<span data-ttu-id="36d8e-138">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-138">1.0</span></span>|  
|`ver_ICorDebugFunctionBreakpoint`|[<span data-ttu-id="36d8e-139">ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="36d8e-139">ICorDebugFunctionBreakpoint</span></span>](icordebugfunctionbreakpoint-interface.md)|<span data-ttu-id="36d8e-140">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-140">1.0</span></span>|  
|`ver_ICorDebugModuleBreakpoint`|[<span data-ttu-id="36d8e-141">ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="36d8e-141">ICorDebugModuleBreakpoint</span></span>](icordebugmodulebreakpoint-interface.md)|<span data-ttu-id="36d8e-142">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-142">1.0</span></span>|  
|`ver_ICorDebugValueBreakpoint`|[<span data-ttu-id="36d8e-143">ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="36d8e-143">ICorDebugValueBreakpoint</span></span>](icordebugvaluebreakpoint-interface.md)|<span data-ttu-id="36d8e-144">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-144">1.0</span></span>|  
|`ver_ICorDebugStepper`|[<span data-ttu-id="36d8e-145">ICorDebugStepper</span><span class="sxs-lookup"><span data-stu-id="36d8e-145">ICorDebugStepper</span></span>](icordebugstepper-interface.md)|<span data-ttu-id="36d8e-146">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-146">1.0</span></span>|  
|`ver_ICorDebugRegisterSet`|[<span data-ttu-id="36d8e-147">ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="36d8e-147">ICorDebugRegisterSet</span></span>](icordebugregisterset-interface.md)|<span data-ttu-id="36d8e-148">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-148">1.0</span></span>|  
|`ver_ICorDebugThread`|[<span data-ttu-id="36d8e-149">ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="36d8e-149">ICorDebugThread</span></span>](icordebugthread-interface.md)|<span data-ttu-id="36d8e-150">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-150">1.0</span></span>|  
|`ver_ICorDebugChain`|[<span data-ttu-id="36d8e-151">ICorDebugChain</span><span class="sxs-lookup"><span data-stu-id="36d8e-151">ICorDebugChain</span></span>](icordebugchain-interface.md)|<span data-ttu-id="36d8e-152">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-152">1.0</span></span>|  
|`ver_ICorDebugFrame`|[<span data-ttu-id="36d8e-153">ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="36d8e-153">ICorDebugFrame</span></span>](icordebugframe-interface.md)|<span data-ttu-id="36d8e-154">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-154">1.0</span></span>|  
|`ver_ICorDebugILFrame`|[<span data-ttu-id="36d8e-155">ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="36d8e-155">ICorDebugILFrame</span></span>](icordebugilframe-interface.md)|<span data-ttu-id="36d8e-156">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-156">1.0</span></span>|  
|`ver_ICorDebugNativeFrame`|[<span data-ttu-id="36d8e-157">ICorDebugNativeFrame</span><span class="sxs-lookup"><span data-stu-id="36d8e-157">ICorDebugNativeFrame</span></span>](icordebugnativeframe-interface.md)|<span data-ttu-id="36d8e-158">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-158">1.0</span></span>|  
|`ver_ICorDebugModule`|[<span data-ttu-id="36d8e-159">ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="36d8e-159">ICorDebugModule</span></span>](icordebugmodule-interface.md)|<span data-ttu-id="36d8e-160">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-160">1.0</span></span>|  
|`ver_ICorDebugFunction`|[<span data-ttu-id="36d8e-161">ICorDebugFunction</span><span class="sxs-lookup"><span data-stu-id="36d8e-161">ICorDebugFunction</span></span>](icordebugfunction-interface1.md)|<span data-ttu-id="36d8e-162">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-162">1.0</span></span>|  
|`ver_ICorDebugCode`|[<span data-ttu-id="36d8e-163">ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="36d8e-163">ICorDebugCode</span></span>](icordebugcode-interface1.md)|<span data-ttu-id="36d8e-164">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-164">1.0</span></span>|  
|`ver_ICorDebugClass`|[<span data-ttu-id="36d8e-165">ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="36d8e-165">ICorDebugClass</span></span>](icordebugclass-interface.md)|<span data-ttu-id="36d8e-166">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-166">1.0</span></span>|  
|`ver_ICorDebugEval`|[<span data-ttu-id="36d8e-167">ICorDebugEval</span><span class="sxs-lookup"><span data-stu-id="36d8e-167">ICorDebugEval</span></span>](icordebugeval-interface.md)|<span data-ttu-id="36d8e-168">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-168">1.0</span></span>|  
|`ver_ICorDebugValue`|[<span data-ttu-id="36d8e-169">ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="36d8e-169">ICorDebugValue</span></span>](icordebugvalue-interface.md)|<span data-ttu-id="36d8e-170">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-170">1.0</span></span>|  
|`ver_ICorDebugGenericValue`|[<span data-ttu-id="36d8e-171">ICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="36d8e-171">ICorDebugGenericValue</span></span>](icordebuggenericvalue-interface.md)|<span data-ttu-id="36d8e-172">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-172">1.0</span></span>|  
|`ver_ICorDebugReferenceValue`|[<span data-ttu-id="36d8e-173">ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="36d8e-173">ICorDebugReferenceValue</span></span>](icordebugreferencevalue-interface.md)|<span data-ttu-id="36d8e-174">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-174">1.0</span></span>|  
|`ver_ICorDebugHeapValue`|[<span data-ttu-id="36d8e-175">ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="36d8e-175">ICorDebugHeapValue</span></span>](icordebugheapvalue-interface.md)|<span data-ttu-id="36d8e-176">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-176">1.0</span></span>|  
|`ver_ICorDebugObjectValue`|[<span data-ttu-id="36d8e-177">ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="36d8e-177">ICorDebugObjectValue</span></span>](icordebugobjectvalue-interface.md)|<span data-ttu-id="36d8e-178">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-178">1.0</span></span>|  
|`ver_ICorDebugBoxValue`|[<span data-ttu-id="36d8e-179">ICorDebugBoxValue</span><span class="sxs-lookup"><span data-stu-id="36d8e-179">ICorDebugBoxValue</span></span>](icordebugboxvalue-interface.md)|<span data-ttu-id="36d8e-180">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-180">1.0</span></span>|  
|`ver_ICorDebugStringValue`|[<span data-ttu-id="36d8e-181">ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="36d8e-181">ICorDebugStringValue</span></span>](icordebugstringvalue-interface.md)|<span data-ttu-id="36d8e-182">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-182">1.0</span></span>|  
|`ver_ICorDebugArrayValue`|[<span data-ttu-id="36d8e-183">ICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="36d8e-183">ICorDebugArrayValue</span></span>](icordebugarrayvalue-interface.md)|<span data-ttu-id="36d8e-184">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-184">1.0</span></span>|  
|`ver_ICorDebugContext`|[<span data-ttu-id="36d8e-185">ICorDebugContext</span><span class="sxs-lookup"><span data-stu-id="36d8e-185">ICorDebugContext</span></span>](icordebugcontext-interface.md)|<span data-ttu-id="36d8e-186">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-186">1.0</span></span>|  
|`ver_ICorDebugEnum`|[<span data-ttu-id="36d8e-187">ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="36d8e-187">ICorDebugEnum</span></span>](icordebugenum-interface1.md)|<span data-ttu-id="36d8e-188">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-188">1.0</span></span>|  
|`ver_ICorDebugObjectEnum`|[<span data-ttu-id="36d8e-189">ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="36d8e-189">ICorDebugObjectEnum</span></span>](icordebugobjectenum-interface.md)|<span data-ttu-id="36d8e-190">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-190">1.0</span></span>|  
|`ver_ICorDebugBreakpointEnum`|[<span data-ttu-id="36d8e-191">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="36d8e-191">ICorDebugBreakpointEnum</span></span>](icordebugbreakpointenum-interface.md)|<span data-ttu-id="36d8e-192">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-192">1.0</span></span>|  
|`ver_ICorDebugStepperEnum`|[<span data-ttu-id="36d8e-193">ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="36d8e-193">ICorDebugStepperEnum</span></span>](icordebugstepperenum-interface.md)|<span data-ttu-id="36d8e-194">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-194">1.0</span></span>|  
|`ver_ICorDebugProcessEnum`|[<span data-ttu-id="36d8e-195">ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="36d8e-195">ICorDebugProcessEnum</span></span>](icordebugprocessenum-interface.md)|<span data-ttu-id="36d8e-196">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-196">1.0</span></span>|  
|`ver_ICorDebugThreadEnum`|[<span data-ttu-id="36d8e-197">ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="36d8e-197">ICorDebugThreadEnum</span></span>](icordebugthreadenum-interface1.md)|<span data-ttu-id="36d8e-198">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-198">1.0</span></span>|  
|`ver_ICorDebugFrameEnum`|[<span data-ttu-id="36d8e-199">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="36d8e-199">ICorDebugFrameEnum</span></span>](icordebugframeenum-interface.md)|<span data-ttu-id="36d8e-200">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-200">1.0</span></span>|  
|`ver_ICorDebugChainEnum`|[<span data-ttu-id="36d8e-201">ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="36d8e-201">ICorDebugChainEnum</span></span>](icordebugchainenum-interface.md)|<span data-ttu-id="36d8e-202">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-202">1.0</span></span>|  
|`ver_ICorDebugModuleEnum`|[<span data-ttu-id="36d8e-203">ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="36d8e-203">ICorDebugModuleEnum</span></span>](icordebugmoduleenum-interface.md)|<span data-ttu-id="36d8e-204">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-204">1.0</span></span>|  
|`ver_ICorDebugValueEnum`|[<span data-ttu-id="36d8e-205">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="36d8e-205">ICorDebugValueEnum</span></span>](icordebugvalueenum-interface.md)|<span data-ttu-id="36d8e-206">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-206">1.0</span></span>|  
|`ver_ICorDebugCodeEnum`|[<span data-ttu-id="36d8e-207">ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="36d8e-207">ICorDebugCodeEnum</span></span>](icordebugcodeenum-interface.md)|<span data-ttu-id="36d8e-208">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-208">1.0</span></span>|  
|`ver_ICorDebugTypeEnum`|[<span data-ttu-id="36d8e-209">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="36d8e-209">ICorDebugTypeEnum</span></span>](icordebugtypeenum-interface.md)|<span data-ttu-id="36d8e-210">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-210">1.0</span></span>|  
|`ver_ICorDebugErrorInfoEnum`|[<span data-ttu-id="36d8e-211">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="36d8e-211">ICorDebugErrorInfoEnum</span></span>](icordebugerrorinfoenum-interface.md)|<span data-ttu-id="36d8e-212">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-212">1.0</span></span>|  
|`ver_ICorDebugAppDomainEnum`|[<span data-ttu-id="36d8e-213">ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="36d8e-213">ICorDebugAppDomainEnum</span></span>](icordebugappdomainenum-interface.md)|<span data-ttu-id="36d8e-214">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-214">1.0</span></span>|  
|`ver_ICorDebugAssemblyEnum`|[<span data-ttu-id="36d8e-215">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="36d8e-215">ICorDebugAssemblyEnum</span></span>](icordebugassemblyenum-interface.md)|<span data-ttu-id="36d8e-216">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-216">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueErrorInfo`|[<span data-ttu-id="36d8e-217">ICorDebugEditAndContinueErrorInfo</span><span class="sxs-lookup"><span data-stu-id="36d8e-217">ICorDebugEditAndContinueErrorInfo</span></span>](icordebugeditandcontinueerrorinfo-interface.md)|<span data-ttu-id="36d8e-218">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-218">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueSnapshot`|[<span data-ttu-id="36d8e-219">ICorDebugEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="36d8e-219">ICorDebugEditAndContinueSnapshot</span></span>](icordebugeditandcontinuesnapshot-interface.md)|<span data-ttu-id="36d8e-220">1.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-220">1.0</span></span>|  
|`ver_ICorDebugManagedCallback2`|[<span data-ttu-id="36d8e-221">ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="36d8e-221">ICorDebugManagedCallback2</span></span>](icordebugmanagedcallback2-interface.md)|<span data-ttu-id="36d8e-222">2.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-222">2.0</span></span>|  
|`ver_ICorDebugAppDomain2`|[<span data-ttu-id="36d8e-223">ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="36d8e-223">ICorDebugAppDomain2</span></span>](icordebugappdomain2-interface.md)|<span data-ttu-id="36d8e-224">2.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-224">2.0</span></span>|  
|`ver_ICorDebugProcess2`|[<span data-ttu-id="36d8e-225">ICorDebugProcess2</span><span class="sxs-lookup"><span data-stu-id="36d8e-225">ICorDebugProcess2</span></span>](icordebugprocess2-interface1.md)|<span data-ttu-id="36d8e-226">2.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-226">2.0</span></span>|  
|`ver_ICorDebugStepper2`|[<span data-ttu-id="36d8e-227">ICorDebugStepper2</span><span class="sxs-lookup"><span data-stu-id="36d8e-227">ICorDebugStepper2</span></span>](icordebugstepper2-interface1.md)|<span data-ttu-id="36d8e-228">2.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-228">2.0</span></span>|  
|`ver_ICorDebugRegisterSet2`|[<span data-ttu-id="36d8e-229">ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="36d8e-229">ICorDebugRegisterSet2</span></span>](icordebugregisterset2-interface.md)|<span data-ttu-id="36d8e-230">2.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-230">2.0</span></span>|  
|`ver_ICorDebugThread2`|[<span data-ttu-id="36d8e-231">ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="36d8e-231">ICorDebugThread2</span></span>](icordebugthread2-interface.md)|<span data-ttu-id="36d8e-232">2.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-232">2.0</span></span>|  
|`ver_ICorDebugILFrame2`|[<span data-ttu-id="36d8e-233">ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="36d8e-233">ICorDebugILFrame2</span></span>](icordebugilframe2-interface.md)|<span data-ttu-id="36d8e-234">2.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-234">2.0</span></span>|  
|`ver_ICorDebugModule2`|[<span data-ttu-id="36d8e-235">ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="36d8e-235">ICorDebugModule2</span></span>](icordebugmodule2-interface.md)|<span data-ttu-id="36d8e-236">2.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-236">2.0</span></span>|  
|`ver_ICorDebugFunction2`|[<span data-ttu-id="36d8e-237">ICorDebugFunction2</span><span class="sxs-lookup"><span data-stu-id="36d8e-237">ICorDebugFunction2</span></span>](icordebugfunction2-interface.md)|<span data-ttu-id="36d8e-238">2.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-238">2.0</span></span>|  
|`ver_ICorDebugCode2`|[<span data-ttu-id="36d8e-239">ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="36d8e-239">ICorDebugCode2</span></span>](icordebugcode2-interface.md)|<span data-ttu-id="36d8e-240">2.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-240">2.0</span></span>|  
|`ver_ICorDebugClass2`|<span data-ttu-id="36d8e-241">ICorDebugClass2</span><span class="sxs-lookup"><span data-stu-id="36d8e-241">"ICorDebugClass2"</span></span>|<span data-ttu-id="36d8e-242">2.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-242">2.0</span></span>|  
|`ver_ICorDebugValue2`|<span data-ttu-id="36d8e-243">ICorDebugValue2</span><span class="sxs-lookup"><span data-stu-id="36d8e-243">"ICorDebugValue2"</span></span>|<span data-ttu-id="36d8e-244">2.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-244">2.0</span></span>|  
|`ver_ICorDebugEval2`|<span data-ttu-id="36d8e-245">"ICorDebugEval2"입니다.</span><span class="sxs-lookup"><span data-stu-id="36d8e-245">The "ICorDebugEval2".</span></span>|<span data-ttu-id="36d8e-246">2.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-246">2.0</span></span>|  
|`ver_ICorDebugObjectValue2`|<span data-ttu-id="36d8e-247">ICorDebugObjectValue2</span><span class="sxs-lookup"><span data-stu-id="36d8e-247">"ICorDebugObjectValue2"</span></span>|<span data-ttu-id="36d8e-248">2.0</span><span class="sxs-lookup"><span data-stu-id="36d8e-248">2.0</span></span>|  
|`ver_ICorDebugThread3`|[<span data-ttu-id="36d8e-249">ICorDebugThread3</span><span class="sxs-lookup"><span data-stu-id="36d8e-249">ICorDebugThread3</span></span>](icordebugthread3-interface.md)|<span data-ttu-id="36d8e-250">4</span><span class="sxs-lookup"><span data-stu-id="36d8e-250">4</span></span>|  
|`ver_ICorDebugThread4`|[<span data-ttu-id="36d8e-251">ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="36d8e-251">ICorDebugThread4</span></span>](icordebugthread4-interface.md)|<span data-ttu-id="36d8e-252">4</span><span class="sxs-lookup"><span data-stu-id="36d8e-252">4</span></span>|  
|`ver_ICorDebugStackWalk`|[<span data-ttu-id="36d8e-253">ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="36d8e-253">ICorDebugStackWalk</span></span>](icordebugstackwalk-interface.md)|<span data-ttu-id="36d8e-254">4</span><span class="sxs-lookup"><span data-stu-id="36d8e-254">4</span></span>|  
|`ver_ICorDebugNativeFrame2`|[<span data-ttu-id="36d8e-255">ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="36d8e-255">ICorDebugNativeFrame2</span></span>](icordebugnativeframe2-interface.md)|<span data-ttu-id="36d8e-256">4</span><span class="sxs-lookup"><span data-stu-id="36d8e-256">4</span></span>|  
|`ver_ICorDebugInternalFrame2`|[<span data-ttu-id="36d8e-257">ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="36d8e-257">ICorDebugInternalFrame2</span></span>](icordebuginternalframe2-interface.md)|<span data-ttu-id="36d8e-258">4</span><span class="sxs-lookup"><span data-stu-id="36d8e-258">4</span></span>|  
|`ver_ICorDebugRuntimeUnwindableFrame`|[<span data-ttu-id="36d8e-259">ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="36d8e-259">ICorDebugRuntimeUnwindableFrame</span></span>](icordebugruntimeunwindableframe-interface.md)|<span data-ttu-id="36d8e-260">4</span><span class="sxs-lookup"><span data-stu-id="36d8e-260">4</span></span>|  
|`ver_ICorDebugHeapValue3`|[<span data-ttu-id="36d8e-261">ICorDebugHeapValue3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="36d8e-261">ICorDebugHeapValue3 Interface</span></span>](icordebugheapvalue3-interface.md)|<span data-ttu-id="36d8e-262">4</span><span class="sxs-lookup"><span data-stu-id="36d8e-262">4</span></span>|  
|`ver_ICorDebugBlockingObjectEnum`|[<span data-ttu-id="36d8e-263">ICorDebugBlockingObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="36d8e-263">ICorDebugBlockingObjectEnum Interface</span></span>](icordebugblockingobjectenum-interface.md)|<span data-ttu-id="36d8e-264">4</span><span class="sxs-lookup"><span data-stu-id="36d8e-264">4</span></span>|  
|`ver_ICorDebugValue3`|[<span data-ttu-id="36d8e-265">ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="36d8e-265">ICorDebugValue3</span></span>](icordebugvalue3-interface.md)|<span data-ttu-id="36d8e-266">4</span><span class="sxs-lookup"><span data-stu-id="36d8e-266">4</span></span>|  
|`ver_ICorDebugComObjectValue`|[<span data-ttu-id="36d8e-267">ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="36d8e-267">ICorDebugComObjectValue</span></span>](icordebugcomobjectvalue-interface.md)|<span data-ttu-id="36d8e-268">4.5.</span><span class="sxs-lookup"><span data-stu-id="36d8e-268">4.5</span></span>|  
|`ver_ICorDebugAppDomain3`|[<span data-ttu-id="36d8e-269">ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="36d8e-269">ICorDebugAppDomain3</span></span>](icordebugappdomain3-interface.md)|<span data-ttu-id="36d8e-270">4.5.</span><span class="sxs-lookup"><span data-stu-id="36d8e-270">4.5</span></span>|  
|`ver_ICorDebugCode3`|[<span data-ttu-id="36d8e-271">ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="36d8e-271">ICorDebugCode3</span></span>](icordebugcode3-interface.md)|<span data-ttu-id="36d8e-272">4.5.</span><span class="sxs-lookup"><span data-stu-id="36d8e-272">4.5</span></span>|  
|`ver_ICorDebugILFrame3`|[<span data-ttu-id="36d8e-273">ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="36d8e-273">ICorDebugILFrame3</span></span>](icordebugilframe3-interface.md)|<span data-ttu-id="36d8e-274">4.5.</span><span class="sxs-lookup"><span data-stu-id="36d8e-274">4.5</span></span>|  
|`CorDebugLatestVersion`|<span data-ttu-id="36d8e-275">모든 서비스 팩을 포함한 .NET Framework 버전이 최신 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="36d8e-275">The version of the .NET Framework, including all of its service packs, is the latest version.</span></span>|-|  
  
## <a name="remarks"></a><span data-ttu-id="36d8e-276">설명</span><span class="sxs-lookup"><span data-stu-id="36d8e-276">Remarks</span></span>  

 <span data-ttu-id="36d8e-277">디버거는 `CorDebugInterfaceVersion` [CreateDebuggingInterfaceFromVersion](../hosting/createdebugginginterfacefromversion-function.md) 함수에서 열거형을 사용 하 여 디버거가 지 원하는 .NET Framework의 가장 높은 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36d8e-277">A debugger can use the `CorDebugInterfaceVersion` enumeration in the [CreateDebuggingInterfaceFromVersion](../hosting/createdebugginginterfacefromversion-function.md) function to specify the highest version of the .NET Framework that the debugger supports.</span></span>  
  
## <a name="interface-names"></a><span data-ttu-id="36d8e-278">인터페이스 이름</span><span class="sxs-lookup"><span data-stu-id="36d8e-278">Interface Names</span></span>  

 <span data-ttu-id="36d8e-279">디버깅 API에서 인터페이스 이름 끝에 표시되는 숫자(예: `ICorDebugThread3`의 경우 "3")는 .NET Framework의 버전이 아닌 인터페이스의 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="36d8e-279">The number that appears at the end of the interface names in the debugging API (for example, the "3" in `ICorDebugThread3`) specifies the version of the interface, not the version of the .NET Framework.</span></span> <span data-ttu-id="36d8e-280">.NET Framework 버전 1에 처음 도입된 인터페이스를 제외하면 디버깅 API의 모든 인터페이스 이름에는 버전 번호가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="36d8e-280">All interface names in the debugging API include version numbers except for interfaces that were introduced in the .NET Framework version 1.</span></span> <span data-ttu-id="36d8e-281">인터페이스 버전 번호와 .NET Framework 버전 번호가 일치하는 경우 단순히 우연적인 일입니다.</span><span class="sxs-lookup"><span data-stu-id="36d8e-281">Any correspondence between interface version numbers and.NET Framework version numbers are coincidental.</span></span>  
  
- <span data-ttu-id="36d8e-282">.NET Framework 버전 1.0에 도입된 인터페이스의 경우 모두 암시적으로 버전 1이므로 번호를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36d8e-282">Interfaces that were introduced in the .NET Framework version 1.0 do not include numbers, because they are all implicitly version 1.</span></span>  
  
- <span data-ttu-id="36d8e-283">.NET Framework 버전 1.1은 버전 1.0 인터페이스를 사용하며 새로운 디버깅 인터페이스는 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36d8e-283">The .NET Framework version 1.1 uses version 1.0 interfaces, and does not introduce any new debugging interfaces.</span></span>  
  
- <span data-ttu-id="36d8e-284">.NET Framework 버전 2.0에 도입된 14개 디버깅 인터페이스는 버전 1의 해당 인터페이스가 논리적으로 확장된 것이며 이름에 숫자 "2"가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="36d8e-284">The 14 debugging interfaces introduced in the .NET Framework version 2.0 are logical extensions of their version 1 counterparts and include the number "2" in their names.</span></span>  
  
- <span data-ttu-id="36d8e-285">.NET Framework 버전 3.0 및 3.5는 기존 .NET Framework 2.0 인터페이스를 사용하며 새로운 인터페이스는 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36d8e-285">The .NET Framework versions 3.0 and 3.5 use the existing .NET Framework 2.0 interfaces, and do not introduce any new interfaces.</span></span>  
  
- <span data-ttu-id="36d8e-286">.NET Framework 4는 인터페이스 버전을 혼합 해 서 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="36d8e-286">The .NET Framework 4 introduces a mix of interface versions.</span></span> <span data-ttu-id="36d8e-287">예를 들어 `ICorDebugThread3` 및 `ICorDebugThread4`는 모두 `ICorDebugThread` 인터페이스의 3번째/4번째 버전으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="36d8e-287">For example, both `ICorDebugThread3` and `ICorDebugThread4` appear as the third and fourth versions of the `ICorDebugThread` interface.</span></span> <span data-ttu-id="36d8e-288">.NET Framework 4에는 인터페이스의 첫 번째 버전과 `ICorDebugStackWalk` 두 번째 버전의 `ICorDebugNativeFrame` 인터페이스 ()도 도입 `ICorDebugNativeFrame2` 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="36d8e-288">The .NET Framework 4 also introduces the first version of the `ICorDebugStackWalk` interface and the second version of the `ICorDebugNativeFrame` interface (`ICorDebugNativeFrame2`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36d8e-289">요구 사항</span><span class="sxs-lookup"><span data-stu-id="36d8e-289">Requirements</span></span>  

 <span data-ttu-id="36d8e-290">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36d8e-290">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36d8e-291">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="36d8e-291">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36d8e-292">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36d8e-292">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36d8e-293">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36d8e-293">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36d8e-294">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36d8e-294">See also</span></span>

- [<span data-ttu-id="36d8e-295">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="36d8e-295">Debugging Enumerations</span></span>](debugging-enumerations.md)
