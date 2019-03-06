---
title: StrongNameSignatureVerificationEx2 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameSignatureVerificationEx2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameSignatureVerificationEx2
helpviewer_keywords:
- StrongNameSignatureVerificationEx2 method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameSignatureVerificationEx2 method [.NET Framework hosting]
ms.assetid: dfd4133f-a074-4db3-a7ee-4f250fe9ad3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc8b3096bd0c60e826fec4c8daf535c3c4086630
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482784"
---
# <a name="strongnamesignatureverificationex2-method"></a><span data-ttu-id="6998f-102">StrongNameSignatureVerificationEx2 메서드</span><span class="sxs-lookup"><span data-stu-id="6998f-102">StrongNameSignatureVerificationEx2 Method</span></span>
<span data-ttu-id="6998f-103">강력한 이름의 어셈블리의 서명을 확인 하 고 실제 키에 대 한 매핑을 ECMA 키에서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6998f-103">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6998f-104">구문</span><span class="sxs-lookup"><span data-stu-id="6998f-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6998f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6998f-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="6998f-106">[in] 이식 가능한 실행 파일 (.exe 또는.dll) 파일에 확인할 어셈블리에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6998f-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="6998f-107">[in] `true` 것이 고, 그렇지 않으면 레지스트리 설정을 재정의 해야 하는 경우에 확인 하는 데 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="6998f-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pbEcmaPublicKey`  
 <span data-ttu-id="6998f-108">[in] 확인에 대 한 실제 키 ECMA 공개 키에서 매핑에 대 한 포인터를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6998f-108">[in] A pointer to the mapping from the ECMA public key to the real key used for verification.</span></span>  
  
 `cbEcmaPublicKey`  
 <span data-ttu-id="6998f-109">[in] 실제 ECMA 공개 키의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="6998f-109">[in] The length of the real ECMA public key.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="6998f-110">[out] `true` 강력한 이름 서명을 확인 했으면이 고, 그렇지 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="6998f-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="6998f-111">이 매개 변수는 또한 설정 `false` 레지스트리 설정으로 인해 성공 했는지 확인 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="6998f-111">This parameter is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6998f-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="6998f-112">Return Value</span></span>  
 <span data-ttu-id="6998f-113">`S_OK` 확인에 성공 하면 그렇지 않으면 실패를 나타내는 HRESULT 값을 (참조 [일반적인 HRESULT 값](https://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="6998f-113">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6998f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6998f-114">Requirements</span></span>  
 <span data-ttu-id="6998f-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6998f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6998f-116">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6998f-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6998f-117">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6998f-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6998f-118">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6998f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6998f-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="6998f-119">See also</span></span>
- [<span data-ttu-id="6998f-120">StrongNameSignatureVerification 메서드</span><span class="sxs-lookup"><span data-stu-id="6998f-120">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="6998f-121">StrongNameSignatureVerificationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="6998f-121">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="6998f-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6998f-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
