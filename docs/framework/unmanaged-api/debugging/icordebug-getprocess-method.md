---
description: '자세히 알아보기: ICorDebug:: GetProcess 메서드'
title: ICorDebug::GetProcess 메서드
ms.date: 03/30/2017
api_name:
- ICorDebug.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::GetProcess method [.NET Framework debugging]
ms.assetid: 10a40ba0-1b65-4721-bd11-cf12d57b280d
topic_type:
- apiref
ms.openlocfilehash: a24bb0ec645a337b1202b954c165a76bcf8fad9d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801308"
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="53ca7-103">ICorDebug::GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="53ca7-103">ICorDebug::GetProcess Method</span></span>

<span data-ttu-id="53ca7-104">지정 된 프로세스에 대 한 "ICorDebugProcess" 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="53ca7-104">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53ca7-105">구문</span><span class="sxs-lookup"><span data-stu-id="53ca7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53ca7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="53ca7-106">Parameters</span></span>  

 `dwProcessId`  
 <span data-ttu-id="53ca7-107">진행 프로세스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="53ca7-107">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="53ca7-108">제한이 지정 된 프로세스의 인스턴스 주소에 `ICorDebugProcess` 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="53ca7-108">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53ca7-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="53ca7-109">Requirements</span></span>  

 <span data-ttu-id="53ca7-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="53ca7-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53ca7-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="53ca7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53ca7-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53ca7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53ca7-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53ca7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53ca7-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53ca7-114">See also</span></span>

- [<span data-ttu-id="53ca7-115">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="53ca7-115">ICorDebug Interface</span></span>](icordebug-interface.md)
