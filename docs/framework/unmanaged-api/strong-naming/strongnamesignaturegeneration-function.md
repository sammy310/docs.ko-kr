---
description: '자세히 알아보기: StrongNameSignatureGeneration 함수'
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
ms.openlocfilehash: 6f5a164e73af743cdd13390c60d00d553e5e0312
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798903"
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="e20b2-103">StrongNameSignatureGeneration 함수</span><span class="sxs-lookup"><span data-stu-id="e20b2-103">StrongNameSignatureGeneration Function</span></span>

<span data-ttu-id="e20b2-104">지정된 어셈블리에 대한 강력한 이름 서명을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e20b2-104">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="e20b2-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e20b2-105">This function has been deprecated.</span></span> <span data-ttu-id="e20b2-106">대신 [ICLRStrongName:: StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e20b2-106">Use the [ICLRStrongName::StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e20b2-107">구문</span><span class="sxs-lookup"><span data-stu-id="e20b2-107">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="e20b2-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e20b2-108">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="e20b2-109">진행 강력한 이름 서명이 생성 될 어셈블리의 매니페스트가 포함 된 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="e20b2-109">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="e20b2-110">진행 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e20b2-110">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="e20b2-111">가 null 인 경우는 `pbKeyBlob` `wszKeyContainer` CSP (암호화 서비스 공급자) 내에 올바른 컨테이너를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e20b2-111">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="e20b2-112">이 경우 컨테이너에 저장 된 키 쌍을 사용 하 여 파일에 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e20b2-112">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="e20b2-113">`pbKeyBlob`가 null이 아닌 경우 키 쌍은 키 BLOB (binary large object)에 포함 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e20b2-113">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="e20b2-114">키는 1024 비트 RSA (Rivest Rivest-shamir-adleman Rivest-shamir-adleman) 서명 키 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e20b2-114">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="e20b2-115">지금은 다른 유형의 키를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e20b2-115">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="e20b2-116">진행 공개/개인 키 쌍에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e20b2-116">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="e20b2-117">이 쌍은 Win32 함수에서 만든 형식입니다 `CryptExportKey` .</span><span class="sxs-lookup"><span data-stu-id="e20b2-117">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="e20b2-118">가 null 인 경우에 `pbKeyBlob` 지정 된 키 컨테이너는 `wszKeyContainer` 키 쌍을 포함 하는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e20b2-118">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="e20b2-119">진행 의 크기 (바이트)입니다 `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="e20b2-119">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="e20b2-120">제한이 공용 언어 런타임에서 서명을 반환 하는 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e20b2-120">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="e20b2-121">`ppbSignatureBlob`가 null 이면 런타임에서는에 지정 된 파일에 서명을 저장 합니다 `wszFilePath` .</span><span class="sxs-lookup"><span data-stu-id="e20b2-121">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="e20b2-122">`ppbSignatureBlob`가 null이 아닌 경우 공용 언어 런타임은 서명을 반환할 공간을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e20b2-122">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="e20b2-123">호출자는 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 함수를 사용 하 여이 공간을 확보 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e20b2-123">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="e20b2-124">제한이 반환 된 시그니처의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="e20b2-124">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e20b2-125">Return Value</span><span class="sxs-lookup"><span data-stu-id="e20b2-125">Return Value</span></span>  

 <span data-ttu-id="e20b2-126">`true` 성공적으로 완료 되 면 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="e20b2-126">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e20b2-127">설명</span><span class="sxs-lookup"><span data-stu-id="e20b2-127">Remarks</span></span>  

 <span data-ttu-id="e20b2-128">에 대해 null `wszFilePath` 을 지정 하 여 서명을 만들지 않고 서명의 크기를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="e20b2-128">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="e20b2-129">시그니처는 파일에 직접 저장 되거나 호출자에 게 반환 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e20b2-129">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="e20b2-130">`StrongNameSignatureGeneration`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e20b2-130">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e20b2-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e20b2-131">Requirements</span></span>  

 <span data-ttu-id="e20b2-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e20b2-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e20b2-133">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="e20b2-133">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e20b2-134">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e20b2-134">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e20b2-135">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e20b2-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e20b2-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e20b2-136">See also</span></span>

- [<span data-ttu-id="e20b2-137">StrongNameSignatureGeneration 메서드</span><span class="sxs-lookup"><span data-stu-id="e20b2-137">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="e20b2-138">StrongNameSignatureGenerationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="e20b2-138">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="e20b2-139">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e20b2-139">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
