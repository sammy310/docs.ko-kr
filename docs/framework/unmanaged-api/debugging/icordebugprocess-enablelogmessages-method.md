---
description: '자세히 알아보기: ICorDebugProcess:: EnableLogMessages 메서드'
title: ICorDebugProcess::EnableLogMessages 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnableLogMessages
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnableLogMessages
helpviewer_keywords:
- ICorDebugProcess::EnableLogMessages method [.NET Framework debugging]
- EnableLogMessages method [.NET Framework debugging]
ms.assetid: 14a4e5a3-3eaf-4f53-9dd1-762726963a23
topic_type:
- apiref
ms.openlocfilehash: d44f1a14611493372c7321feaa14329d5d77b01b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753993"
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="47447-103">ICorDebugProcess::EnableLogMessages 메서드</span><span class="sxs-lookup"><span data-stu-id="47447-103">ICorDebugProcess::EnableLogMessages Method</span></span>

<span data-ttu-id="47447-104">디버거로 로그 메시지 전송을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="47447-104">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47447-105">구문</span><span class="sxs-lookup"><span data-stu-id="47447-105">Syntax</span></span>  
  
```cpp  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47447-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="47447-106">Parameters</span></span>  

 `fOnOff`  
 <span data-ttu-id="47447-107">[in] `true` 로그 메시지를 전송할 수 있도록 합니다. `false` 전송을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="47447-107">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47447-108">설명</span><span class="sxs-lookup"><span data-stu-id="47447-108">Remarks</span></span>  

 <span data-ttu-id="47447-109">이 메서드는 [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) 콜백이 발생 한 후에만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="47447-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47447-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="47447-110">Requirements</span></span>  

 <span data-ttu-id="47447-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47447-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47447-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47447-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47447-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47447-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47447-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47447-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
