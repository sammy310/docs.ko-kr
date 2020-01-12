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
ms.openlocfilehash: ced7540afe931fb91240c770d76d205400157a51
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901096"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="c6d9a-102">ICLRStrongName::StrongNameSignatureGeneration 메서드</span><span class="sxs-lookup"><span data-stu-id="c6d9a-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="c6d9a-103">지정된 어셈블리에 대한 강력한 이름 서명을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6d9a-104">구문</span><span class="sxs-lookup"><span data-stu-id="c6d9a-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c6d9a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c6d9a-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="c6d9a-106">진행 강력한 이름 서명이 생성 될 어셈블리의 매니페스트가 포함 된 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="c6d9a-107">진행 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="c6d9a-108">`pbKeyBlob`가 null 인 경우에는 CSP (암호화 서비스 공급자) 내에 올바른 컨테이너를 지정 해야 `wszKeyContainer`.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="c6d9a-109">이 경우 컨테이너에 저장 된 키 쌍을 사용 하 여 파일에 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="c6d9a-110">`pbKeyBlob`가 null이 아닌 경우 키 쌍은 키 BLOB (binary large object)에 포함 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="c6d9a-111">키는 1024 비트 RSA (Rivest Rivest-shamir-adleman Rivest-shamir-adleman) 서명 키 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="c6d9a-112">지금은 다른 유형의 키를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="c6d9a-113">진행 공개/개인 키 쌍에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="c6d9a-114">이 쌍은 Win32 `CryptExportKey` 함수에 의해 생성 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="c6d9a-115">`pbKeyBlob` null 인 경우 `wszKeyContainer`에 의해 지정 된 키 컨테이너는 키 쌍을 포함 하는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="c6d9a-116">진행 `pbKeyBlob`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="c6d9a-117">제한이 공용 언어 런타임에서 서명을 반환 하는 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="c6d9a-118">`ppbSignatureBlob`가 null 이면 런타임은 `wszFilePath`에 지정 된 파일에 서명을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="c6d9a-119">`ppbSignatureBlob`가 null이 아닌 경우 공용 언어 런타임은 서명을 반환할 공간을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="c6d9a-120">호출자는 [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드를 사용 하 여이 공간을 확보 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="c6d9a-121">제한이 반환 된 시그니처의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6d9a-122">반환 값</span><span class="sxs-lookup"><span data-stu-id="c6d9a-122">Return Value</span></span>  
 <span data-ttu-id="c6d9a-123">메서드가 성공적으로 완료 되 면 `S_OK` 하 고, 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="c6d9a-123">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6d9a-124">주의</span><span class="sxs-lookup"><span data-stu-id="c6d9a-124">Remarks</span></span>  
 <span data-ttu-id="c6d9a-125">서명을 만들지 않고 시그니처의 크기를 계산 하려면 `wszFilePath`에 대해 null을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="c6d9a-126">시그니처는 파일에 직접 저장 되거나 호출자에 게 반환 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6d9a-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6d9a-127">Requirements</span></span>  
 <span data-ttu-id="c6d9a-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6d9a-129">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="c6d9a-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c6d9a-130">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6d9a-131">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6d9a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6d9a-132">참조</span><span class="sxs-lookup"><span data-stu-id="c6d9a-132">See also</span></span>

- [<span data-ttu-id="c6d9a-133">StrongNameSignatureGenerationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="c6d9a-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="c6d9a-134">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6d9a-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
