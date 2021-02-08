---
description: '자세한 정보: Silverlight 용 CreateDebuggingInterfaceFromVersion 함수'
title: Silverlight용 CreateDebuggingInterfaceFromVersion 함수
ms.date: 03/30/2017
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
ms.openlocfilehash: 8c61593f2e912260ecca65efce9f905ce56e88dc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801451"
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a><span data-ttu-id="d345c-103">Silverlight용 CreateDebuggingInterfaceFromVersion 함수</span><span class="sxs-lookup"><span data-stu-id="d345c-103">CreateDebuggingInterfaceFromVersion Function for Silverlight</span></span>

<span data-ttu-id="d345c-104">[Createversionstringfrommodule 함수](createversionstringfrommodule-function.md)에서 반환 되는 CLR (공용 언어 런타임) 버전 문자열을 수락 하 고 해당 디버거 인터페이스 (일반적으로 [ICorDebug](icordebug-interface.md))를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d345c-104">Accepts a common language runtime (CLR) version string that is returned from the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md), and returns a corresponding debugger interface (typically, [ICorDebug](icordebug-interface.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d345c-105">구문</span><span class="sxs-lookup"><span data-stu-id="d345c-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d345c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d345c-106">Parameters</span></span>  

 `szDebuggeeVersion`\
 <span data-ttu-id="d345c-107">진행 [Createversionstringfrommodule 함수](createversionstringfrommodule-function.md)에서 반환 하는 대상 디버기에 있는 CLR의 버전 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d345c-107">[in] Version string of the CLR in the target debuggee, which is returned by the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md).</span></span>  
  
 `ppCordb`\
 <span data-ttu-id="d345c-108">[out] COM 개체(`IUnknown`)에 대한 포인터의 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d345c-108">[out] Pointer to a pointer to a COM object (`IUnknown`).</span></span> <span data-ttu-id="d345c-109">이 개체는 반환 되기 전에 [ICorDebug](icordebug-interface.md) 개체로 캐스팅 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d345c-109">This object will be cast to an [ICorDebug](icordebug-interface.md) object before it is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d345c-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="d345c-110">Return Value</span></span>

 `S_OK`\
 <span data-ttu-id="d345c-111">`ppCordb`[ICorDebug interface](icordebug-interface.md) 인터페이스를 구현 하는 유효한 개체를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="d345c-111">`ppCordb` references a valid object that implements the [ICorDebug interface](icordebug-interface.md) interface.</span></span>  
  
 `E_INVALIDARG`\
 <span data-ttu-id="d345c-112">`szDebuggeeVersion` 또는 `ppCordb`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="d345c-112">Either `szDebuggeeVersion` or `ppCordb` is null.</span></span>  
  
 `CORDBG_E_DEBUG_COMPONENT_MISSING`\
 <span data-ttu-id="d345c-113">CLR 디버깅에 필요한 구성 요소를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d345c-113">A component that is necessary for CLR debugging cannot be located.</span></span> <span data-ttu-id="d345c-114">대상 CoreCLR.dll와 동일한 디렉터리에서 _mscordbi.dll_ 또는 _mscordaccore.dll_ 를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d345c-114">Either _mscordbi.dll_ or _mscordaccore.dll_ was not found in the same directory as the target CoreCLR.dll.</span></span>  
  
 `CORDBG_E_INCOMPATIBLE_PROTOCOL`\
 <span data-ttu-id="d345c-115">mscordbi.dll 또는 mscordaccore.dll이 대상 CoreCLR.dll과 동일한 버전이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d345c-115">Either mscordbi.dll or mscordaccore.dll is not the same version as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="d345c-116">`E_FAIL` (또는 다른 `E_` 반환 코드) </span><span class="sxs-lookup"><span data-stu-id="d345c-116">`E_FAIL` (or other `E_` return codes)</span></span>\
 <span data-ttu-id="d345c-117">[ICorDebug 인터페이스](icordebug-interface.md)를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d345c-117">Unable to return an [ICorDebug interface](icordebug-interface.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d345c-118">설명</span><span class="sxs-lookup"><span data-stu-id="d345c-118">Remarks</span></span>

 <span data-ttu-id="d345c-119">반환된 인터페이스는 대상 프로세스의 CLR에 연결하고 CLR에서 실행 중인 관리 코드를 디버그하기 위한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d345c-119">The interface that is returned provides the facilities for attaching to a CLR in a target process and debugging the managed code that the CLR is running.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d345c-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d345c-120">Requirements</span></span>

 <span data-ttu-id="d345c-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d345c-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d345c-122">**헤더:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="d345c-122">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="d345c-123">**라이브러리:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="d345c-123">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="d345c-124">**.NET Framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="d345c-124">**.NET Framework Versions:** 3.5 SP1</span></span>
