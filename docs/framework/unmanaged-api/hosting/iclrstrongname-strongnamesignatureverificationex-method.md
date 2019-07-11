---
title: ICLRStrongName::StrongNameSignatureVerificationEx 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureVerificationEx method [.NET Framework hosting]
ms.assetid: dbd2f662-208b-4174-b301-5c99af91040f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 32d6f3040cbb2070433ad5e3b6117d4b0b212656
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765879"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a><span data-ttu-id="2a0a5-102">ICLRStrongName::StrongNameSignatureVerificationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="2a0a5-102">ICLRStrongName::StrongNameSignatureVerificationEx Method</span></span>
<span data-ttu-id="2a0a5-103">강력한 이름 시그니처를 어셈블리 매니페스트에 제공 된 경로 포함 되는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2a0a5-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a0a5-104">구문</span><span class="sxs-lookup"><span data-stu-id="2a0a5-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a0a5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2a0a5-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="2a0a5-106">[in] 이식 가능한 실행 파일 (.exe 또는.dll) 파일에 확인할 어셈블리에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2a0a5-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="2a0a5-107">[in] `true` 것이 고, 그렇지 않으면 레지스트리 설정을 재정의 해야 하는 경우에 확인 하는 데 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0a5-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="2a0a5-108">[out] `true` 강력한 이름 서명을 확인 했으면이 고, 그렇지 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0a5-108">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="2a0a5-109">`pfWasVerified` 또한로 `false` 레지스트리 설정으로 인해 성공 했는지 확인 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="2a0a5-109">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a0a5-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="2a0a5-110">Return Value</span></span>  
 <span data-ttu-id="2a0a5-111">`S_OK` 확인에 성공 하면 그렇지 않으면 실패를 나타내는 HRESULT 값을 (참조 [일반적인 HRESULT 값](https://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="2a0a5-111">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a0a5-112">설명</span><span class="sxs-lookup"><span data-stu-id="2a0a5-112">Remarks</span></span>  
 <span data-ttu-id="2a0a5-113">합니다 [iclrstrongname:: Strongnamesignatureverificationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) 메서드는 유사한 기능을 제공 합니다 [iclrstrongname:: Strongnamesignatureverification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="2a0a5-113">The [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method provides a capability similar to the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method.</span></span> <span data-ttu-id="2a0a5-114">그러나 두 번째 입력 매개 변수와 출력 매개 변수를 [iclrstrongname:: Strongnamesignatureverificationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) 형식의 `BOOLEAN` 대신 `DWORD`합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0a5-114">However, the second input parameter and the output parameter for [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a0a5-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2a0a5-115">Requirements</span></span>  
 <span data-ttu-id="2a0a5-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2a0a5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a0a5-117">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="2a0a5-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2a0a5-118">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2a0a5-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a0a5-119">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a0a5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a0a5-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="2a0a5-120">See also</span></span>

- [<span data-ttu-id="2a0a5-121">StrongNameSignatureVerification 메서드</span><span class="sxs-lookup"><span data-stu-id="2a0a5-121">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="2a0a5-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a0a5-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
