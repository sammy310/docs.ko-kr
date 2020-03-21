---
title: StrongNameSignatureGeneration 함수
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
ms.openlocfilehash: d7f481e5c61ec65d2e7414bd47227866f3435028
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176905"
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="99b55-102">StrongNameSignatureGeneration 함수</span><span class="sxs-lookup"><span data-stu-id="99b55-102">StrongNameSignatureGeneration Function</span></span>
<span data-ttu-id="99b55-103">지정된 어셈블리에 대한 강력한 이름 서명을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="99b55-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="99b55-104">이 함수는 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99b55-104">This function has been deprecated.</span></span> <span data-ttu-id="99b55-105">대신 [ICLRStrongName::강력한 이름 서명 생성](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="99b55-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99b55-106">구문</span><span class="sxs-lookup"><span data-stu-id="99b55-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureGeneration (
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99b55-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="99b55-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="99b55-108">【인】 강력한 이름 서명이 생성되는 어셈블리의 매니페스트가 포함된 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="99b55-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="99b55-109">【인】 공개/개인 키 쌍을 포함하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="99b55-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="99b55-110">null인 `pbKeyBlob` `wszKeyContainer` 경우 CSP(암호화 서비스 공급자) 내에서 유효한 컨테이너를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b55-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="99b55-111">이 경우 컨테이너에 저장된 키 쌍이 파일에 서명하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="99b55-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="99b55-112">null이 아닌 경우 `pbKeyBlob` 키 쌍은 키 이진 큰 개체(BLOB)에 포함되는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="99b55-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="99b55-113">키는 1024비트 Rivest-Shamir-Adleman(RSA) 서명 키여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b55-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="99b55-114">현재 다른 유형의 키는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99b55-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="99b55-115">【인】 공용/개인 키 쌍에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="99b55-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="99b55-116">이 쌍은 Win32 `CryptExportKey` 함수에서 만든 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="99b55-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="99b55-117">null인 경우 `pbKeyBlob` 지정한 `wszKeyContainer` 키 컨테이너는 키 쌍을 포함하는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="99b55-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="99b55-118">【인】 의 크기(바이트)입니다. `pbKeyBlob`</span><span class="sxs-lookup"><span data-stu-id="99b55-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="99b55-119">【아웃】 공통 언어 런타임이 서명을 반환하는 위치에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="99b55-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="99b55-120">null인 경우 `ppbSignatureBlob` 런타임은 에 의해 지정된 `wszFilePath`파일에 서명을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="99b55-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="99b55-121">null이 아닌 경우 `ppbSignatureBlob` 공통 언어 런타임은 서명을 반환할 공간을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="99b55-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="99b55-122">호출자는 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 함수를 사용하여 이 공간을 확보해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99b55-122">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="99b55-123">【아웃】 반환된 서명의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="99b55-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99b55-124">Return Value</span><span class="sxs-lookup"><span data-stu-id="99b55-124">Return Value</span></span>  
 <span data-ttu-id="99b55-125">`true`성공적인 완료시; 그렇지 `false`않으면 .</span><span class="sxs-lookup"><span data-stu-id="99b55-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99b55-126">설명</span><span class="sxs-lookup"><span data-stu-id="99b55-126">Remarks</span></span>  
 <span data-ttu-id="99b55-127">서명을 만들지 `wszFilePath` 않고 서명 크기를 계산하려면 null을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="99b55-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="99b55-128">서명을 파일에 직접 저장하거나 호출자에게 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99b55-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="99b55-129">`StrongNameSignatureGeneration`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="99b55-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99b55-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99b55-130">Requirements</span></span>  
 <span data-ttu-id="99b55-131">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99b55-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99b55-132">**헤더:** 스트롱네임</span><span class="sxs-lookup"><span data-stu-id="99b55-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="99b55-133">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="99b55-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="99b55-134">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99b55-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99b55-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99b55-135">See also</span></span>

- [<span data-ttu-id="99b55-136">StrongNameSignatureGeneration 메서드</span><span class="sxs-lookup"><span data-stu-id="99b55-136">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="99b55-137">StrongNameSignatureGenerationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="99b55-137">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="99b55-138">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99b55-138">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
