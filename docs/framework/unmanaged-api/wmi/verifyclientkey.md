---
title: 검증클라이언트키 기능(관리되지 않는 API 참조)
description: VerifyClientKey 기능은 클라이언트 키에 올바른 보안을 보장합니다.
ms.date: 11/06/2017
api_name:
- VerifyClientKey
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- VerifyClientKey
helpviewer_keywords:
- VerifyClientKey function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: ebb794240494deb0c831b50e95461ec52017a215
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176710"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="39f0f-103">검증클라이언트키 기능</span><span class="sxs-lookup"><span data-stu-id="39f0f-103">VerifyClientKey function</span></span>
<span data-ttu-id="39f0f-104">클라이언트 키가 올바른 보안을 유지하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="39f0f-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="39f0f-105">구문</span><span class="sxs-lookup"><span data-stu-id="39f0f-105">Syntax</span></span>  
  
```cpp  
LONG VerifyClientKey();
```  

## <a name="return-value"></a><span data-ttu-id="39f0f-106">반환 값</span><span class="sxs-lookup"><span data-stu-id="39f0f-106">Return value</span></span>

<span data-ttu-id="39f0f-107">함수가 성공하면 반환 값은 `ERROR_SUCCESS` (0)입니다.</span><span class="sxs-lookup"><span data-stu-id="39f0f-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="39f0f-108">함수가 실패하면 반환 값은 *WinError.h에*정의된 0이 아닌 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="39f0f-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="39f0f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="39f0f-109">Requirements</span></span>  
 <span data-ttu-id="39f0f-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39f0f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39f0f-111">**헤더:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="39f0f-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="39f0f-112">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="39f0f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39f0f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39f0f-113">See also</span></span>

- [<span data-ttu-id="39f0f-114">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="39f0f-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
