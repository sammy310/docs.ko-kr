---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8062ab151efc6175aa68cb0563cd2ad042ee9cd8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189055"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="c1ea1-102">FLockClrVersionCallback 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="c1ea1-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="c1ea1-103">해당 초기화를 나타내기 위해 공용 언어 런타임 (CLR) 호출 시작 또는 완료 하는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="c1ea1-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="c1ea1-104">이 함수 포인터에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ea1-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1ea1-105">구문</span><span class="sxs-lookup"><span data-stu-id="c1ea1-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="c1ea1-106">설명</span><span class="sxs-lookup"><span data-stu-id="c1ea1-106">Remarks</span></span>  
 <span data-ttu-id="c1ea1-107">이 함수는 호스트에서 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1ea1-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1ea1-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1ea1-108">Requirements</span></span>  
 <span data-ttu-id="c1ea1-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c1ea1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1ea1-110">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c1ea1-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c1ea1-111">**라이브러리:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="c1ea1-111">**Library:** MSCorWks.dll</span></span>  
  
 **<span data-ttu-id="c1ea1-112">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="c1ea1-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c1ea1-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="c1ea1-113">See also</span></span>

- [<span data-ttu-id="c1ea1-114">LockClrVersion 함수</span><span class="sxs-lookup"><span data-stu-id="c1ea1-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [<span data-ttu-id="c1ea1-115">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="c1ea1-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
