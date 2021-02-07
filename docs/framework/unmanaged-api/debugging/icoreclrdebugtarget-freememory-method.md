---
description: '자세히 알아보기: ICoreClrDebugTarget:: FreeMemory 메서드'
title: ICoreClrDebugTarget::FreeMemory 메서드
ms.date: 03/30/2017
api_name:
- ICoreDebugTarget.FreeMemory
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::FreeMemory
helpviewer_keywords:
- remote debugging API [Silverlight]
- FreeMemory method, ICoreClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::FreeMemory method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 98f2a0db-a6ec-4f9b-861d-f82485237d08
topic_type:
- apiref
ms.openlocfilehash: 9572e0c3df1fdd064e78ba170d39c1415c68dc85
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690004"
---
# <a name="icoreclrdebugtargetfreememory-method"></a><span data-ttu-id="8ee0a-103">ICoreClrDebugTarget::FreeMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="8ee0a-103">ICoreClrDebugTarget::FreeMemory Method</span></span>

<span data-ttu-id="8ee0a-104">[ICoreClrDebugTarget:: enumprocesses](icoreclrdebugtarget-enumprocesses-method.md) 및 [ICoreClrDebugTarget:: enumprocesses](icoreclrdebugtarget-enumruntimes-method.md) 메서드에 의해 할당 된 메모리를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee0a-104">Frees the memory allocated by the [ICoreClrDebugTarget::EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) and [ICoreClrDebugTarget::EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md) methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ee0a-105">구문</span><span class="sxs-lookup"><span data-stu-id="8ee0a-105">Syntax</span></span>  
  
```cpp  
void FreeMemory (  
     [in] void*pMemory);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ee0a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8ee0a-106">Parameters</span></span>  

 `pMemory`  
 <span data-ttu-id="8ee0a-107">진행 [ICoreClrDebugTarget:: enumprocesses](icoreclrdebugtarget-enumprocesses-method.md) 또는 [ICoreClrDebugTarget:: enumprocesses](icoreclrdebugtarget-enumruntimes-method.md) 메서드에 의해 반환 된 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8ee0a-107">[in] A pointer to the array that is returned by either the [ICoreClrDebugTarget::EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) or the [ICoreClrDebugTarget::EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ee0a-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8ee0a-108">Requirements</span></span>  

 <span data-ttu-id="8ee0a-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ee0a-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ee0a-110">**헤더:** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="8ee0a-110">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="8ee0a-111">**라이브러리:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="8ee0a-111">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="8ee0a-112">**.NET Framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="8ee0a-112">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ee0a-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ee0a-113">See also</span></span>

- [<span data-ttu-id="8ee0a-114">ICoreClrDebugTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ee0a-114">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)
