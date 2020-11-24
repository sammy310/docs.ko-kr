---
title: ICorDebugThread2::GetConnectionID 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetConnectionID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetConnectionID
helpviewer_keywords:
- ICorDebugThread2::GetConnectionID method [.NET Framework debugging]
- GetConnectionID method [.NET Framework debugging]
ms.assetid: 9c76b587-f941-4fa1-8b86-f3494fb10c8e
topic_type:
- apiref
ms.openlocfilehash: 1507715e80761c871dfdb0b8d25dc708a2130678
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678690"
---
# <a name="icordebugthread2getconnectionid-method"></a><span data-ttu-id="420b0-102">ICorDebugThread2::GetConnectionID 메서드</span><span class="sxs-lookup"><span data-stu-id="420b0-102">ICorDebugThread2::GetConnectionID Method</span></span>

<span data-ttu-id="420b0-103">이 ICorDebugThread2 개체에 대 한 연결 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="420b0-103">Gets the connection identifier for this ICorDebugThread2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="420b0-104">구문</span><span class="sxs-lookup"><span data-stu-id="420b0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="420b0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="420b0-105">Parameters</span></span>  

 `pdwConnectionId`  
 <span data-ttu-id="420b0-106">제한이 `CONNID` 연결 식별자를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="420b0-106">[out] A `CONNID` that represents the connection identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="420b0-107">설명</span><span class="sxs-lookup"><span data-stu-id="420b0-107">Remarks</span></span>  

 <span data-ttu-id="420b0-108">`GetConnectionID` `pdwConnectionId` 이 스레드가 연결의 일부가 아닌 경우 메서드는 매개 변수에서 0을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="420b0-108">The `GetConnectionID` method returns zero in the `pdwConnectionId` parameter, if this thread is not part of a connection.</span></span>  
  
 <span data-ttu-id="420b0-109">이 스레드가 SSAS (Microsoft SQL Server 2005 Analysis Services)의 인스턴스에 연결 된 경우는 `CONNID` SPID (서버 프로세스 식별자)에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="420b0-109">If this thread is connected to an instance of Microsoft SQL Server 2005 Analysis Services (SSAS), the `CONNID` maps to a server process identifier (SPID).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="420b0-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="420b0-110">Requirements</span></span>  

 <span data-ttu-id="420b0-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="420b0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="420b0-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="420b0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="420b0-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="420b0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="420b0-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="420b0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
