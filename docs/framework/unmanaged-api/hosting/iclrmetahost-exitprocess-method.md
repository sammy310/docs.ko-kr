---
title: ICLRMetaHost::ExitProcess 메서드
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.ExitProcess
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0288c9912125e20cfb9f9aaaac5003ae9e0b51e9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779782"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="18e8f-102">ICLRMetaHost::ExitProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="18e8f-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="18e8f-103">로드 된 모든 런타임을 정상적으로 종료 하 고 프로세스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="18e8f-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="18e8f-104">대체는 [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="18e8f-104">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18e8f-105">구문</span><span class="sxs-lookup"><span data-stu-id="18e8f-105">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18e8f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18e8f-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="18e8f-107">[in] 프로세스 종료 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="18e8f-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18e8f-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="18e8f-108">Return Value</span></span>  
 <span data-ttu-id="18e8f-109">이 메서드가 반환 하지 않으므로 해당 반환 값이 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18e8f-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18e8f-110">설명</span><span class="sxs-lookup"><span data-stu-id="18e8f-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18e8f-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18e8f-111">Requirements</span></span>  
 <span data-ttu-id="18e8f-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="18e8f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18e8f-113">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="18e8f-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="18e8f-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="18e8f-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="18e8f-115">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18e8f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18e8f-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="18e8f-116">See also</span></span>

- [<span data-ttu-id="18e8f-117">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18e8f-117">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="18e8f-118">호스팅</span><span class="sxs-lookup"><span data-stu-id="18e8f-118">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
