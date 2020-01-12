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
ms.openlocfilehash: fbc9ea6aab9f0c3d9be95e6affcd04342ce4c5cc
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901069"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a><span data-ttu-id="59fb7-102">ICLRStrongName::StrongNameSignatureVerificationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="59fb7-102">ICLRStrongName::StrongNameSignatureVerificationEx Method</span></span>
<span data-ttu-id="59fb7-103">제공 된 경로의 어셈블리 매니페스트에 강력한 이름 시그니처가 포함 되어 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="59fb7-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59fb7-104">구문</span><span class="sxs-lookup"><span data-stu-id="59fb7-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59fb7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59fb7-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="59fb7-106">진행 확인할 어셈블리의 이식 가능한 실행 파일 (.exe 또는 .dll) 파일에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="59fb7-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="59fb7-107">[in] 레지스트리 설정을 재정의 해야 하는 경우에도 확인을 수행 `true` 합니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="59fb7-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="59fb7-108">[out] 강력한 이름 서명을 확인 했으면 `true` 합니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="59fb7-108">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="59fb7-109">레지스트리 설정으로 인해 확인이 성공적으로 수행 된 경우에도 `pfWasVerified` `false`로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59fb7-109">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59fb7-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="59fb7-110">Return Value</span></span>  
 <span data-ttu-id="59fb7-111">확인에 성공 하면 `S_OK` 하 고, 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="59fb7-111">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59fb7-112">주의</span><span class="sxs-lookup"><span data-stu-id="59fb7-112">Remarks</span></span>  
 <span data-ttu-id="59fb7-113">[ICLRStrongName:: StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) 메서드는 [ICLRStrongName:: StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) 메서드와 비슷한 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="59fb7-113">The [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method provides a capability similar to the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method.</span></span> <span data-ttu-id="59fb7-114">그러나 [ICLRStrongName:: StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) 에 대 한 두 번째 입력 매개 변수 및 출력 매개 변수는 `DWORD`대신 `BOOLEAN` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="59fb7-114">However, the second input parameter and the output parameter for [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59fb7-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59fb7-115">Requirements</span></span>  
 <span data-ttu-id="59fb7-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59fb7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59fb7-117">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="59fb7-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="59fb7-118">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59fb7-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="59fb7-119">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59fb7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59fb7-120">참조</span><span class="sxs-lookup"><span data-stu-id="59fb7-120">See also</span></span>

- [<span data-ttu-id="59fb7-121">StrongNameSignatureVerification 메서드</span><span class="sxs-lookup"><span data-stu-id="59fb7-121">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="59fb7-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59fb7-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
