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
ms.openlocfilehash: 9ab6fcb64e4654302e411d4dcc587df2e0bf1dc1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125188"
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="d8ce0-102">StrongNameSignatureGeneration 함수</span><span class="sxs-lookup"><span data-stu-id="d8ce0-102">StrongNameSignatureGeneration Function</span></span>
<span data-ttu-id="d8ce0-103">지정된 어셈블리에 대한 강력한 이름 서명을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="d8ce0-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-104">This function has been deprecated.</span></span> <span data-ttu-id="d8ce0-105">대신 [ICLRStrongName:: StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8ce0-106">구문</span><span class="sxs-lookup"><span data-stu-id="d8ce0-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d8ce0-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d8ce0-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="d8ce0-108">진행 강력한 이름 서명이 생성 될 어셈블리의 매니페스트가 포함 된 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="d8ce0-109">진행 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="d8ce0-110">`pbKeyBlob`가 null 인 경우에는 CSP (암호화 서비스 공급자) 내에 올바른 컨테이너를 지정 해야 `wszKeyContainer`.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="d8ce0-111">이 경우 컨테이너에 저장 된 키 쌍을 사용 하 여 파일에 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="d8ce0-112">`pbKeyBlob`가 null이 아닌 경우 키 쌍은 키 BLOB (binary large object)에 포함 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="d8ce0-113">키는 1024 비트 RSA (Rivest Rivest-shamir-adleman Rivest-shamir-adleman) 서명 키 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="d8ce0-114">지금은 다른 유형의 키를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="d8ce0-115">진행 공개/개인 키 쌍에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="d8ce0-116">이 쌍은 Win32 `CryptExportKey` 함수에 의해 생성 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="d8ce0-117">`pbKeyBlob` null 인 경우 `wszKeyContainer`에 의해 지정 된 키 컨테이너는 키 쌍을 포함 하는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="d8ce0-118">진행 `pbKeyBlob`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="d8ce0-119">제한이 공용 언어 런타임에서 서명을 반환 하는 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="d8ce0-120">`ppbSignatureBlob`가 null 이면 런타임은 `wszFilePath`에 지정 된 파일에 서명을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="d8ce0-121">`ppbSignatureBlob`가 null이 아닌 경우 공용 언어 런타임은 서명을 반환할 공간을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="d8ce0-122">호출자는 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 함수를 사용 하 여이 공간을 확보 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-122">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="d8ce0-123">제한이 반환 된 시그니처의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8ce0-124">반환 값</span><span class="sxs-lookup"><span data-stu-id="d8ce0-124">Return Value</span></span>  
 <span data-ttu-id="d8ce0-125">성공적으로 완료 되 면 `true` 합니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8ce0-126">주의</span><span class="sxs-lookup"><span data-stu-id="d8ce0-126">Remarks</span></span>  
 <span data-ttu-id="d8ce0-127">서명을 만들지 않고 시그니처의 크기를 계산 하려면 `wszFilePath`에 대해 null을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="d8ce0-128">시그니처는 파일에 직접 저장 되거나 호출자에 게 반환 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="d8ce0-129">`StrongNameSignatureGeneration` 함수가 성공적으로 완료 되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8ce0-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8ce0-130">Requirements</span></span>  
 <span data-ttu-id="d8ce0-131">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8ce0-132">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="d8ce0-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d8ce0-133">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8ce0-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d8ce0-134">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8ce0-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8ce0-135">참조</span><span class="sxs-lookup"><span data-stu-id="d8ce0-135">See also</span></span>

- [<span data-ttu-id="d8ce0-136">StrongNameSignatureGeneration 메서드</span><span class="sxs-lookup"><span data-stu-id="d8ce0-136">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="d8ce0-137">StrongNameSignatureGenerationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="d8ce0-137">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="d8ce0-138">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8ce0-138">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
