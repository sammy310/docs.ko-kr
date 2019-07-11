---
title: CorExitProcess 함수
ms.date: 03/30/2017
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7aaa0e83de1b1c3e2ce436de04a36addef16c057
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758523"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="d2c8d-102">CorExitProcess 함수</span><span class="sxs-lookup"><span data-stu-id="d2c8d-102">CorExitProcess Function</span></span>
<span data-ttu-id="d2c8d-103">현재 관리 되지 않는 프로세스를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="d2c8d-104">.NET Framework 4에서이 함수에 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="d2c8d-105">사용 된 [iclrmetahost:: Exitprocess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2c8d-106">구문</span><span class="sxs-lookup"><span data-stu-id="d2c8d-106">Syntax</span></span>  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2c8d-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d2c8d-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="d2c8d-108">프로세스 종료 코드를 지정 하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2c8d-109">설명</span><span class="sxs-lookup"><span data-stu-id="d2c8d-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d2c8d-110">.NET Framework 4 부터는 `CorExitProcess` 레거시 Api가 바인딩된 런타임 뿐 아니라 프로세스에서 모든 시작된 된 런타임을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-110">Beginning with the .NET Framework 4, `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2c8d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d2c8d-111">Requirements</span></span>  
 <span data-ttu-id="d2c8d-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2c8d-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d2c8d-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d2c8d-114">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d2c8d-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2c8d-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2c8d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2c8d-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="d2c8d-116">See also</span></span>

- [<span data-ttu-id="d2c8d-117">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="d2c8d-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
