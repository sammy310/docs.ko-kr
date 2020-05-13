---
title: ICorDebugManagedCallback::NameChange 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.NameChange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::NameChange
helpviewer_keywords:
- ICorDebugManagedCallback::NameChange method [.NET Framework debugging]
- NameChange method [.NET Framework debugging]
ms.assetid: a7018a0e-880e-4b68-b52a-1cd22c7aad62
topic_type:
- apiref
ms.openlocfilehash: 48bfce9966ff12fe1b425fbcd9a81860628a54e6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212674"
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="56996-102">ICorDebugManagedCallback::NameChange 메서드</span><span class="sxs-lookup"><span data-stu-id="56996-102">ICorDebugManagedCallback::NameChange Method</span></span>
<span data-ttu-id="56996-103">응용 프로그램 도메인 또는 스레드의 이름이 변경 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="56996-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56996-104">구문</span><span class="sxs-lookup"><span data-stu-id="56996-104">Syntax</span></span>  
  
```cpp  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56996-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="56996-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="56996-106">진행 이름이 변경 되었거나 이름이 변경 된 스레드를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="56996-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="56996-107">진행 이름이 변경 된 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="56996-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56996-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="56996-108">Requirements</span></span>  
 <span data-ttu-id="56996-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56996-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56996-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56996-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56996-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56996-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56996-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56996-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56996-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56996-113">See also</span></span>

- [<span data-ttu-id="56996-114">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="56996-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
