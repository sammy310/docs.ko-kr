---
description: '자세히 알아보기: StrongNameGetPublicKey 함수'
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
ms.openlocfilehash: c94ffdd20e83b03da27b2f44ebbc279cfd8b8afc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670572"
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="31d8a-103">StrongNameGetPublicKey 함수</span><span class="sxs-lookup"><span data-stu-id="31d8a-103">StrongNameGetPublicKey Function</span></span>

<span data-ttu-id="31d8a-104">퍼블릭/퍼블릭 키 쌍에서 퍼블릭 키를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31d8a-104">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="31d8a-105">키 쌍은 CSP (암호화 서비스 공급자) 내에서 키 컨테이너 이름으로 제공 되거나 원시 바이트 컬렉션으로 제공 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d8a-105">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="31d8a-106">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31d8a-106">This function has been deprecated.</span></span> <span data-ttu-id="31d8a-107">대신 [ICLRStrongName:: StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="31d8a-107">Use the [ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31d8a-108">구문</span><span class="sxs-lookup"><span data-stu-id="31d8a-108">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31d8a-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="31d8a-109">Parameters</span></span>  

 `szKeyContainer`  
 <span data-ttu-id="31d8a-110">진행 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="31d8a-110">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="31d8a-111">가 null 인 경우는 `pbKeyBlob` `szKeyContainer` CSP 내에서 유효한 컨테이너를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31d8a-111">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="31d8a-112">이 경우는 `StrongNameGetPublicKey` 컨테이너에 저장 된 키 쌍에서 공개 키를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="31d8a-112">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="31d8a-113">`pbKeyBlob`가 null이 아닌 경우 키 쌍은 키 BLOB (binary large object)에 포함 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31d8a-113">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="31d8a-114">키는 1024 비트 RSA (Rivest Rivest-shamir-adleman Rivest-shamir-adleman) 서명 키 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31d8a-114">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="31d8a-115">지금은 다른 유형의 키를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31d8a-115">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="31d8a-116">진행 공개/개인 키 쌍에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="31d8a-116">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="31d8a-117">이 쌍은 Win32 함수에서 만든 형식입니다 `CryptExportKey` .</span><span class="sxs-lookup"><span data-stu-id="31d8a-117">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="31d8a-118">가 null 인 경우에 `pbKeyBlob` 지정 된 키 컨테이너는 `szKeyContainer` 키 쌍을 포함 하는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31d8a-118">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="31d8a-119">진행 의 크기 (바이트)입니다 `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="31d8a-119">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="31d8a-120">제한이 반환 된 공개 키 BLOB입니다.</span><span class="sxs-lookup"><span data-stu-id="31d8a-120">[out] The returned public key BLOB.</span></span> <span data-ttu-id="31d8a-121">`ppbPublicKeyBlob`매개 변수는 공용 언어 런타임에 의해 할당 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31d8a-121">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="31d8a-122">호출자는 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 함수를 사용 하 여 메모리를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31d8a-122">The caller must free the memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="31d8a-123">제한이 반환 된 공개 키 BLOB의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="31d8a-123">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31d8a-124">Return Value</span><span class="sxs-lookup"><span data-stu-id="31d8a-124">Return Value</span></span>  

 <span data-ttu-id="31d8a-125">`true` 성공적으로 완료 되 면 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="31d8a-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31d8a-126">설명</span><span class="sxs-lookup"><span data-stu-id="31d8a-126">Remarks</span></span>  

 <span data-ttu-id="31d8a-127">공개 키가 [PublicKeyBlob](publickeyblob-structure.md) 구조에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31d8a-127">The public key is contained in a [PublicKeyBlob](publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="31d8a-128">`StrongNameGetPublicKey`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="31d8a-128">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31d8a-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="31d8a-129">Requirements</span></span>  

 <span data-ttu-id="31d8a-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31d8a-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31d8a-131">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="31d8a-131">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="31d8a-132">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31d8a-132">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="31d8a-133">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31d8a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31d8a-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31d8a-134">See also</span></span>

- [<span data-ttu-id="31d8a-135">StrongNameGetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="31d8a-135">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="31d8a-136">StrongNameTokenFromPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="31d8a-136">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="31d8a-137">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="31d8a-137">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="31d8a-138">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="31d8a-138">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
