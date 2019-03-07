---
title: ICLRStrongName::StrongNameGetBlob 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlob
- ICLRStrongName.StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlob
helpviewer_keywords:
- ICLRStrongName::StrongNameGetBlob method [.NET Framework hosting]
- StrongNameGetBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: a24218f8-7196-44be-b7a2-ee9cdd7a85c4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ba606230be7a81fc42644c2fd3883a989bf37ac
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498993"
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="3e380-102">ICLRStrongName::StrongNameGetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="3e380-102">ICLRStrongName::StrongNameGetBlob Method</span></span>
<span data-ttu-id="3e380-103">지정된 주소에 있는 실행 파일의 이진 표현으로 지정된 버퍼를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="3e380-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e380-104">구문</span><span class="sxs-lookup"><span data-stu-id="3e380-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e380-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3e380-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="3e380-106">[in] 유효한 경로 로드 되도록 실행 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="3e380-106">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="3e380-107">[in] 실행 파일을 로드 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="3e380-107">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="3e380-108">[out에서] 최대 크기 (바이트), 요청한 `pbBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="3e380-108">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="3e380-109">실제 크기를 바이트 단위로 반환 될 때의 `pbBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="3e380-109">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e380-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="3e380-110">Return Value</span></span>  
 <span data-ttu-id="3e380-111">`S_OK` 메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값을 (참조 [일반적인 HRESULT 값](https://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="3e380-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e380-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e380-112">Requirements</span></span>  
 <span data-ttu-id="3e380-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3e380-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e380-114">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="3e380-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3e380-115">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3e380-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e380-116">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e380-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e380-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="3e380-117">See also</span></span>
- [<span data-ttu-id="3e380-118">StrongNameGetBlobFromImage 메서드</span><span class="sxs-lookup"><span data-stu-id="3e380-118">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="3e380-119">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3e380-119">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
