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
ms.openlocfilehash: d8643c54950486b6374045ff83928c8c7fb568a9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140942"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="2d5c7-102">ICLRMetaHost::ExitProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="2d5c7-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="2d5c7-103">로드 된 모든 런타임을 정상적으로 종료 하 고 프로세스를 종료 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5c7-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="2d5c7-104">[Corexitprocess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) 함수를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d5c7-104">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d5c7-105">구문</span><span class="sxs-lookup"><span data-stu-id="2d5c7-105">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d5c7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2d5c7-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="2d5c7-107">진행 프로세스의 종료 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2d5c7-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d5c7-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="2d5c7-108">Return Value</span></span>  
 <span data-ttu-id="2d5c7-109">이 메서드는를 반환 하지 않으므로 반환 값이 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d5c7-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d5c7-110">주의</span><span class="sxs-lookup"><span data-stu-id="2d5c7-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d5c7-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2d5c7-111">Requirements</span></span>  
 <span data-ttu-id="2d5c7-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d5c7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d5c7-113">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="2d5c7-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2d5c7-114">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d5c7-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d5c7-115">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d5c7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d5c7-116">참조</span><span class="sxs-lookup"><span data-stu-id="2d5c7-116">See also</span></span>

- [<span data-ttu-id="2d5c7-117">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2d5c7-117">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="2d5c7-118">호스팅</span><span class="sxs-lookup"><span data-stu-id="2d5c7-118">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
