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
ms.openlocfilehash: 5e6f77b9b5da061a75d23d7f3f7b673754b62afd
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006367"
---
# <a name="strongnamesignatureverificationex2-method"></a><span data-ttu-id="25c45-102">StrongNameSignatureVerificationEx2 메서드</span><span class="sxs-lookup"><span data-stu-id="25c45-102">StrongNameSignatureVerificationEx2 Method</span></span>
<span data-ttu-id="25c45-103">강력한 이름의 어셈블리에 대 한 서명을 확인 하 고 ECMA 키에서 실제 키로의 매핑을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="25c45-103">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25c45-104">구문</span><span class="sxs-lookup"><span data-stu-id="25c45-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25c45-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="25c45-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="25c45-106">진행 확인할 어셈블리의 이식 가능한 실행 파일 (.exe 또는 .dll) 파일에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="25c45-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="25c45-107">[in] `true` 레지스트리 설정을 재정의 해야 하는 경우에도 유효성 검사를 수행 하려면 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="25c45-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pbEcmaPublicKey`  
 <span data-ttu-id="25c45-108">진행 유효성 검사에 사용 되는 실제 키에 대 한 ECMA 공개 키의 매핑에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="25c45-108">[in] A pointer to the mapping from the ECMA public key to the real key used for verification.</span></span>  
  
 `cbEcmaPublicKey`  
 <span data-ttu-id="25c45-109">진행 실제 ECMA 공개 키의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="25c45-109">[in] The length of the real ECMA public key.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="25c45-110">[out] `true` 강력한 이름 서명을 확인 했으면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="25c45-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="25c45-111">`false`레지스트리 설정으로 인해 확인이 성공적으로 수행 된 경우에도이 매개 변수는로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25c45-111">This parameter is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25c45-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="25c45-112">Return Value</span></span>  
 <span data-ttu-id="25c45-113">`S_OK`확인에 성공 했으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="25c45-113">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25c45-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="25c45-114">Requirements</span></span>  
 <span data-ttu-id="25c45-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25c45-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25c45-116">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="25c45-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="25c45-117">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25c45-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="25c45-118">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25c45-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25c45-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25c45-119">See also</span></span>

- [<span data-ttu-id="25c45-120">StrongNameSignatureVerification 메서드</span><span class="sxs-lookup"><span data-stu-id="25c45-120">StrongNameSignatureVerification Method</span></span>](iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="25c45-121">StrongNameSignatureVerificationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="25c45-121">StrongNameSignatureVerificationEx Method</span></span>](iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="25c45-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25c45-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
