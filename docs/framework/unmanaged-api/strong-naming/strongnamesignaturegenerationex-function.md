---
title: StrongNameSignatureGenerationEx 함수
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGenerationEx
helpviewer_keywords:
- StrongNameSignatureGenerationEx function [.NET Framework strong naming]
ms.assetid: 9a75469e-aa49-4e32-ad48-3bafd5202f09
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89398c221dcf9d6f89027f15da4062bc7ed67e3f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798988"
---
# <a name="strongnamesignaturegenerationex-function"></a><span data-ttu-id="b0ee2-102">StrongNameSignatureGenerationEx 함수</span><span class="sxs-lookup"><span data-stu-id="b0ee2-102">StrongNameSignatureGenerationEx Function</span></span>
<span data-ttu-id="b0ee2-103">지정 된 플래그에 따라 지정 된 어셈블리에 대 한 강력한 이름 서명을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
 <span data-ttu-id="b0ee2-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-104">This function has been deprecated.</span></span> <span data-ttu-id="b0ee2-105">대신 [ICLRStrongName:: StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-105">Use the [ICLRStrongName::StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0ee2-106">구문</span><span class="sxs-lookup"><span data-stu-id="b0ee2-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0ee2-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b0ee2-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="b0ee2-108">진행 강력한 이름 서명이 생성 될 어셈블리의 매니페스트가 포함 된 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="b0ee2-109">진행 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="b0ee2-110">`pbKeyBlob` 가`wszKeyContainer` null 인 경우는 CSP (암호화 서비스 공급자) 내에 올바른 컨테이너를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="b0ee2-111">이 경우 컨테이너에 저장 된 키 쌍을 사용 하 여 파일에 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="b0ee2-112">가 `pbKeyBlob` null이 아닌 경우 키 쌍은 키 BLOB (binary large object)에 포함 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="b0ee2-113">진행 공개/개인 키 쌍에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="b0ee2-114">이 쌍은 Win32 `CryptExportKey` 함수에서 만든 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="b0ee2-115">가 `pbKeyBlob` null 인 경우에 `wszKeyContainer` 지정 된 키 컨테이너는 키 쌍을 포함 하는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="b0ee2-116">진행 의 `pbKeyBlob`크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="b0ee2-117">제한이 공용 언어 런타임에서 서명을 반환 하는 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="b0ee2-118">가 `ppbSignatureBlob` null 이면 런타임에서는에 `wszFilePath`지정 된 파일에 서명을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="b0ee2-119">가 `ppbSignatureBlob` null이 아닌 경우 공용 언어 런타임은 서명을 반환할 공간을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="b0ee2-120">호출자는 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 함수를 사용 하 여이 공간을 확보 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-120">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="b0ee2-121">제한이 반환 된 시그니처의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b0ee2-122">진행 다음 값 중 하나 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-122">[in] One or more of the following values:</span></span>  
  
- <span data-ttu-id="b0ee2-123">`SN_SIGN_ALL_FILES`(0x00000001)-연결 된 모듈에 대 한 모든 해시를 다시 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-123">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
- <span data-ttu-id="b0ee2-124">`SN_TEST_SIGN`(0x00000002)-어셈블리를 테스트 하 여 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-124">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0ee2-125">반환 값</span><span class="sxs-lookup"><span data-stu-id="b0ee2-125">Return Value</span></span>  
 <span data-ttu-id="b0ee2-126">`true`성공적으로 완료 되 면 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-126">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0ee2-127">설명</span><span class="sxs-lookup"><span data-stu-id="b0ee2-127">Remarks</span></span>  
 <span data-ttu-id="b0ee2-128">에 대해 `wszFilePath` null을 지정 하 여 서명을 만들지 않고 서명의 크기를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-128">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="b0ee2-129">시그니처는 파일에 직접 저장 되거나 호출자에 게 반환 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-129">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="b0ee2-130">가 `SN_SIGN_ALL_FILES` 지정 되었지만 공개 키가 포함 되어 있지 않은 경우 및 `pbKeyBlob` `wszFilePath` 가 모두 null 인 경우 연결 된 모듈에 대 한 해시가 다시 계산 되지만 어셈블리는 다시 서명 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-130">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="b0ee2-131">을 `SN_TEST_SIGN` 지정 하면 어셈블리를 강력한 이름으로 서명 하는 것을 나타내기 위해 공용 언어 런타임 헤더가 수정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-131">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
 <span data-ttu-id="b0ee2-132">`StrongNameSignatureGenerationEx` 함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-132">If the `StrongNameSignatureGenerationEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0ee2-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b0ee2-133">Requirements</span></span>  
 <span data-ttu-id="b0ee2-134">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0ee2-135">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="b0ee2-135">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b0ee2-136">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0ee2-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b0ee2-137">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0ee2-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0ee2-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="b0ee2-138">See also</span></span>

- [<span data-ttu-id="b0ee2-139">StrongNameSignatureGenerationEx 메서드</span><span class="sxs-lookup"><span data-stu-id="b0ee2-139">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="b0ee2-140">StrongNameSignatureGeneration 메서드</span><span class="sxs-lookup"><span data-stu-id="b0ee2-140">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="b0ee2-141">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0ee2-141">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
