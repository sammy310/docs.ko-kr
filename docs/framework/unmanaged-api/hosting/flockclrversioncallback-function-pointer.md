---
description: '자세한 정보: FLockClrVersionCallback 함수 포인터'
title: FLockClrVersionCallback 함수 포인터
ms.date: 03/30/2017
api_name:
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
ms.openlocfilehash: 3506cd30ab2a9e5a06b03f5010c9870280a38378
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785382"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="32f0f-103">FLockClrVersionCallback 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="32f0f-103">FLockClrVersionCallback Function Pointer</span></span>

<span data-ttu-id="32f0f-104">초기화가 시작 되거나 완료 되었음을 나타내기 위해 CLR (공용 언어 런타임)에서 호출 하는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="32f0f-104">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="32f0f-105">이 함수 포인터는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32f0f-105">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32f0f-106">구문</span><span class="sxs-lookup"><span data-stu-id="32f0f-106">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="32f0f-107">설명</span><span class="sxs-lookup"><span data-stu-id="32f0f-107">Remarks</span></span>  

 <span data-ttu-id="32f0f-108">이 함수는 호스트에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32f0f-108">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32f0f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32f0f-109">Requirements</span></span>  

 <span data-ttu-id="32f0f-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32f0f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32f0f-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="32f0f-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32f0f-112">**라이브러리:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="32f0f-112">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="32f0f-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32f0f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32f0f-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32f0f-114">See also</span></span>

- [<span data-ttu-id="32f0f-115">LockClrVersion 함수</span><span class="sxs-lookup"><span data-stu-id="32f0f-115">LockClrVersion Function</span></span>](lockclrversion-function.md)
- [<span data-ttu-id="32f0f-116">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="32f0f-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
