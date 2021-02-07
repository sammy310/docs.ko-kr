---
description: '자세히 알아보기: StrongNameSignatureVerificationEx2 메서드'
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
ms.openlocfilehash: d79491744ce1a930693d2901544ad80bf8049544
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679279"
---
# <a name="strongnamesignatureverificationex2-method"></a><span data-ttu-id="58d69-103">StrongNameSignatureVerificationEx2 메서드</span><span class="sxs-lookup"><span data-stu-id="58d69-103">StrongNameSignatureVerificationEx2 Method</span></span>

<span data-ttu-id="58d69-104">강력한 이름의 어셈블리에 대 한 서명을 확인 하 고 ECMA 키에서 실제 키로의 매핑을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="58d69-104">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58d69-105">구문</span><span class="sxs-lookup"><span data-stu-id="58d69-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58d69-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="58d69-106">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="58d69-107">진행 확인할 어셈블리의 이식 가능한 실행 파일 (.exe 또는 .dll) 파일에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="58d69-107">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="58d69-108">[in] `true` 레지스트리 설정을 재정의 해야 하는 경우에도 유효성 검사를 수행 하려면 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="58d69-108">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pbEcmaPublicKey`  
 <span data-ttu-id="58d69-109">진행 유효성 검사에 사용 되는 실제 키에 대 한 ECMA 공개 키의 매핑에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="58d69-109">[in] A pointer to the mapping from the ECMA public key to the real key used for verification.</span></span>  
  
 `cbEcmaPublicKey`  
 <span data-ttu-id="58d69-110">진행 실제 ECMA 공개 키의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="58d69-110">[in] The length of the real ECMA public key.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="58d69-111">[out] `true` 강력한 이름 서명을 확인 했으면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="58d69-111">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="58d69-112">`false`레지스트리 설정으로 인해 확인이 성공적으로 수행 된 경우에도이 매개 변수는로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58d69-112">This parameter is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58d69-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="58d69-113">Return Value</span></span>  

 <span data-ttu-id="58d69-114">`S_OK` 확인에 성공 했으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="58d69-114">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58d69-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="58d69-115">Requirements</span></span>  

 <span data-ttu-id="58d69-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58d69-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58d69-117">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="58d69-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="58d69-118">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58d69-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58d69-119">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58d69-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58d69-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58d69-120">See also</span></span>

- [<span data-ttu-id="58d69-121">StrongNameSignatureVerification 메서드</span><span class="sxs-lookup"><span data-stu-id="58d69-121">StrongNameSignatureVerification Method</span></span>](iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="58d69-122">StrongNameSignatureVerificationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="58d69-122">StrongNameSignatureVerificationEx Method</span></span>](iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="58d69-123">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="58d69-123">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
