---
title: ICLRStrongName::StrongNameSignatureGeneration 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGeneration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureGeneration method [.NET Framework hosting]
ms.assetid: 4cdb1284-947a-4ed4-94c1-c5ff5cdfce56
topic_type:
- apiref
ms.openlocfilehash: e58ac181c4e472c469076b880ff71e0c6afa30fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178048"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="4529b-102">ICLRStrongName::StrongNameSignatureGeneration 메서드</span><span class="sxs-lookup"><span data-stu-id="4529b-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="4529b-103">지정된 어셈블리에 대한 강력한 이름 서명을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4529b-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4529b-104">구문</span><span class="sxs-lookup"><span data-stu-id="4529b-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureGeneration (
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4529b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4529b-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="4529b-106">【인】 강력한 이름 서명이 생성되는 어셈블리의 매니페스트가 포함된 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="4529b-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="4529b-107">【인】 공개/개인 키 쌍을 포함하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4529b-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="4529b-108">null인 `pbKeyBlob` `wszKeyContainer` 경우 CSP(암호화 서비스 공급자) 내에서 유효한 컨테이너를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4529b-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="4529b-109">이 경우 컨테이너에 저장된 키 쌍이 파일에 서명하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4529b-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="4529b-110">null이 아닌 경우 `pbKeyBlob` 키 쌍은 키 이진 큰 개체(BLOB)에 포함되는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="4529b-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="4529b-111">키는 1024비트 Rivest-Shamir-Adleman(RSA) 서명 키여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4529b-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="4529b-112">현재 다른 유형의 키는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4529b-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="4529b-113">【인】 공용/개인 키 쌍에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4529b-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="4529b-114">이 쌍은 Win32 `CryptExportKey` 함수에서 만든 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4529b-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="4529b-115">null인 경우 `pbKeyBlob` 지정한 `wszKeyContainer` 키 컨테이너는 키 쌍을 포함하는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="4529b-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="4529b-116">【인】 의 크기(바이트)입니다. `pbKeyBlob`</span><span class="sxs-lookup"><span data-stu-id="4529b-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="4529b-117">【아웃】 공통 언어 런타임이 서명을 반환하는 위치에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4529b-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="4529b-118">null인 경우 `ppbSignatureBlob` 런타임은 에 의해 지정된 `wszFilePath`파일에 서명을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4529b-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="4529b-119">null이 아닌 경우 `ppbSignatureBlob` 공통 언어 런타임은 서명을 반환할 공간을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4529b-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="4529b-120">호출자는 [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드를 사용하여 이 공간을 확보해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4529b-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="4529b-121">【아웃】 반환된 서명의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="4529b-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4529b-122">Return Value</span><span class="sxs-lookup"><span data-stu-id="4529b-122">Return Value</span></span>  
 <span data-ttu-id="4529b-123">`S_OK`메서드가 성공적으로 완료된 경우 그렇지 않으면 실패를 나타내는 HRESULT 값입니다(목록의 [공통 HRESULT 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="4529b-123">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4529b-124">설명</span><span class="sxs-lookup"><span data-stu-id="4529b-124">Remarks</span></span>  
 <span data-ttu-id="4529b-125">서명을 만들지 `wszFilePath` 않고 서명 크기를 계산하려면 null을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4529b-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="4529b-126">서명을 파일에 직접 저장하거나 호출자에게 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4529b-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4529b-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4529b-127">Requirements</span></span>  
 <span data-ttu-id="4529b-128">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4529b-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4529b-129">**헤더:** 메타호스트</span><span class="sxs-lookup"><span data-stu-id="4529b-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4529b-130">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="4529b-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4529b-131">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4529b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4529b-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4529b-132">See also</span></span>

- [<span data-ttu-id="4529b-133">StrongNameSignatureGenerationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="4529b-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="4529b-134">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4529b-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
