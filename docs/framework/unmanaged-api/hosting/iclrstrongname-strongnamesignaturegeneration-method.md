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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 679afd7b1053043a7cc43304a544a516024a4696
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165785"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="dc0f5-102">ICLRStrongName::StrongNameSignatureGeneration 메서드</span><span class="sxs-lookup"><span data-stu-id="dc0f5-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="dc0f5-103">지정된 어셈블리에 대한 강력한 이름 서명을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0f5-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc0f5-104">구문</span><span class="sxs-lookup"><span data-stu-id="dc0f5-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc0f5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dc0f5-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="dc0f5-106">[in] 강력한 이름 시그니처를 생성 하는 어셈블리의 매니페스트가 포함 된 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="dc0f5-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="dc0f5-107">[in] 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dc0f5-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="dc0f5-108">하는 경우 `pbKeyBlob` 이 null 이면 `wszKeyContainer` 암호화 서비스 공급자 (CSP) 내에서 유효한 컨테이너를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0f5-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="dc0f5-109">이 경우 컨테이너에 저장 된 키 쌍 파일에 서명 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc0f5-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="dc0f5-110">경우 `pbKeyBlob` null이 아니면 키 쌍 가정 키 binary large object (BLOB)에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0f5-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="dc0f5-111">키에는 1024 비트 adleman의 Rivest-Shamir (RSA) 키를 서명 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0f5-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="dc0f5-112">다른 종류의 키이 이번에 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc0f5-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="dc0f5-113">[in] 공개/개인 키 쌍에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dc0f5-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="dc0f5-114">이 쌍이 win32 만들어진 형식을 `CryptExportKey` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="dc0f5-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="dc0f5-115">하는 경우 `pbKeyBlob` 가 null 이면 지정 된 키 컨테이너 `wszKeyContainer` 키 쌍을 포함 하도록 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc0f5-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="dc0f5-116">[in] 크기 (바이트)의 `pbKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0f5-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="dc0f5-117">[out] 공용 언어 런타임 시그니처를 반환 하는 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dc0f5-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="dc0f5-118">하는 경우 `ppbSignatureBlob` 가 null 이면 런타임에서 서명을 저장 하 여 지정한 파일에 `wszFilePath`입니다.</span><span class="sxs-lookup"><span data-stu-id="dc0f5-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="dc0f5-119">경우 `ppbSignatureBlob` 는 null이 아닌 공용 언어 런타임 시그니처를 반환 하는 공간을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0f5-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="dc0f5-120">호출자에 게 사용 하 여이 공간을 해제 해야 합니다 [iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="dc0f5-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="dc0f5-121">[out] 반환 된 서명의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="dc0f5-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc0f5-122">반환 값</span><span class="sxs-lookup"><span data-stu-id="dc0f5-122">Return Value</span></span>  
 `S_OK` <span data-ttu-id="dc0f5-123">메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값을 (참조 [일반적인 HRESULT 값](https://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="dc0f5-123">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc0f5-124">설명</span><span class="sxs-lookup"><span data-stu-id="dc0f5-124">Remarks</span></span>  
 <span data-ttu-id="dc0f5-125">Null을 지정 `wszFilePath` 시그니처를 만들지 않고 서명의 크기를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0f5-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="dc0f5-126">서명을 수 파일에 직접 저장 하거나 또는 호출자에 게 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc0f5-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc0f5-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dc0f5-127">Requirements</span></span>  
 <span data-ttu-id="dc0f5-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc0f5-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc0f5-129">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="dc0f5-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="dc0f5-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="dc0f5-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="dc0f5-131">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="dc0f5-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dc0f5-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="dc0f5-132">See also</span></span>

- [<span data-ttu-id="dc0f5-133">StrongNameSignatureGenerationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="dc0f5-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="dc0f5-134">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dc0f5-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
