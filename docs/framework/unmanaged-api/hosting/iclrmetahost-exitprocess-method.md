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
ms.openlocfilehash: 6d601ac3ece801353b630c74ed852c2657f25d7f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730465"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="c854f-102">ICLRMetaHost::ExitProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="c854f-102">ICLRMetaHost::ExitProcess Method</span></span>

<span data-ttu-id="c854f-103">로드 된 모든 런타임을 정상적으로 종료 하 고 프로세스를 종료 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c854f-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="c854f-104">[Corexitprocess](corexitprocess-function.md) 함수를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="c854f-104">Supersedes the [CorExitProcess](corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c854f-105">구문</span><span class="sxs-lookup"><span data-stu-id="c854f-105">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c854f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c854f-106">Parameters</span></span>  

 `iExitCode`  
 <span data-ttu-id="c854f-107">진행 프로세스의 종료 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c854f-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c854f-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="c854f-108">Return Value</span></span>  

 <span data-ttu-id="c854f-109">이 메서드는를 반환 하지 않으므로 반환 값이 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c854f-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c854f-110">설명</span><span class="sxs-lookup"><span data-stu-id="c854f-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c854f-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c854f-111">Requirements</span></span>  

 <span data-ttu-id="c854f-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c854f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c854f-113">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="c854f-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c854f-114">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c854f-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c854f-115">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c854f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c854f-116">참조</span><span class="sxs-lookup"><span data-stu-id="c854f-116">See also</span></span>

- [<span data-ttu-id="c854f-117">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c854f-117">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="c854f-118">호스팅</span><span class="sxs-lookup"><span data-stu-id="c854f-118">Hosting</span></span>](index.md)
