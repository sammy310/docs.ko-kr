---
title: StrongNameGetPublicKey 함수
ms.date: 03/30/2017
api_name:
- StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type:
- apiref
ms.openlocfilehash: fcdd4a3f07b4499fd2388b5d165c409da9150466
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176931"
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="9346b-102">StrongNameGetPublicKey 함수</span><span class="sxs-lookup"><span data-stu-id="9346b-102">StrongNameGetPublicKey Function</span></span>
<span data-ttu-id="9346b-103">퍼블릭/퍼블릭 키 쌍에서 퍼블릭 키를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9346b-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="9346b-104">키 쌍은 CSP(암호화 서비스 공급자) 내에서 키 컨테이너 이름으로 또는 원시 바이트 컬렉션으로 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9346b-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="9346b-105">이 함수는 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9346b-105">This function has been deprecated.</span></span> <span data-ttu-id="9346b-106">대신 [ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9346b-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9346b-107">구문</span><span class="sxs-lookup"><span data-stu-id="9346b-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9346b-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9346b-108">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="9346b-109">【인】 공개/개인 키 쌍을 포함하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9346b-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="9346b-110">null인 `pbKeyBlob` 경우 `szKeyContainer` CSP 내에서 유효한 컨테이너를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9346b-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="9346b-111">이 경우 `StrongNameGetPublicKey` 컨테이너에 저장된 키 쌍에서 공개 키를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="9346b-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="9346b-112">null이 아닌 경우 `pbKeyBlob` 키 쌍은 키 이진 큰 개체(BLOB)에 포함되는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="9346b-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="9346b-113">키는 1024비트 Rivest-Shamir-Adleman(RSA) 서명 키여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9346b-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="9346b-114">현재 다른 유형의 키는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9346b-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="9346b-115">【인】 공용/개인 키 쌍에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9346b-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="9346b-116">이 쌍은 Win32 `CryptExportKey` 함수에서 만든 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9346b-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="9346b-117">null인 경우 `pbKeyBlob` 지정한 `szKeyContainer` 키 컨테이너는 키 쌍을 포함하는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="9346b-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="9346b-118">【인】 의 크기(바이트)입니다. `pbKeyBlob`</span><span class="sxs-lookup"><span data-stu-id="9346b-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="9346b-119">【아웃】 반환된 공개 키 BLOB입니다.</span><span class="sxs-lookup"><span data-stu-id="9346b-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="9346b-120">매개 `ppbPublicKeyBlob` 변수는 공통 언어 런타임에 의해 할당되고 호출자에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9346b-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="9346b-121">호출자는 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 함수를 사용하여 메모리를 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9346b-121">The caller must free the memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="9346b-122">【아웃】 반환된 공개 키 BLOB의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9346b-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9346b-123">Return Value</span><span class="sxs-lookup"><span data-stu-id="9346b-123">Return Value</span></span>  
 <span data-ttu-id="9346b-124">`true`성공적인 완료시; 그렇지 `false`않으면 .</span><span class="sxs-lookup"><span data-stu-id="9346b-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9346b-125">설명</span><span class="sxs-lookup"><span data-stu-id="9346b-125">Remarks</span></span>  
 <span data-ttu-id="9346b-126">공개 키는 [PublicKeyBlob](publickeyblob-structure.md) 구조에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9346b-126">The public key is contained in a [PublicKeyBlob](publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="9346b-127">`StrongNameGetPublicKey`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9346b-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9346b-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9346b-128">Requirements</span></span>  
 <span data-ttu-id="9346b-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9346b-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9346b-130">**헤더:** 스트롱네임</span><span class="sxs-lookup"><span data-stu-id="9346b-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="9346b-131">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9346b-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9346b-132">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9346b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9346b-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9346b-133">See also</span></span>

- [<span data-ttu-id="9346b-134">StrongNameGetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="9346b-134">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="9346b-135">StrongNameTokenFromPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="9346b-135">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="9346b-136">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9346b-136">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="9346b-137">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="9346b-137">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
