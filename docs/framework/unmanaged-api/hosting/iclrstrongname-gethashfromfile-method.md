---
title: ICLRStrongName::GetHashFromFile 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromFile method [.NET Framework hosting]
- GetHashFromFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 9e50480a-8ada-4044-b2a5-97bb14ed3525
topic_type:
- apiref
ms.openlocfilehash: ff346d8f7ba321904a8d91079298b58039e6eb54
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727616"
---
# <a name="iclrstrongnamegethashfromfile-method"></a><span data-ttu-id="8a277-102">ICLRStrongName::GetHashFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="8a277-102">ICLRStrongName::GetHashFromFile Method</span></span>

<span data-ttu-id="8a277-103">지정된 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8a277-103">Generates a hash over the contents of the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a277-104">구문</span><span class="sxs-lookup"><span data-stu-id="8a277-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a277-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8a277-105">Parameters</span></span>  

 `szFilePath`  
 <span data-ttu-id="8a277-106">진행 해시할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8a277-106">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="8a277-107">[in, out] 해시를 생성할 때 사용할 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="8a277-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="8a277-108">유효한 알고리즘은 Win32 CryptoAPI에서 정의 되는 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="8a277-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="8a277-109">`piHashAlg`가 0으로 설정 되 면 기본 알고리즘 CALG_SHA-1이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a277-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="8a277-110">제한이 생성 된 해시를 포함 하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="8a277-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="8a277-111">진행 가 가리키는 버퍼의 최대 크기입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="8a277-111">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="8a277-112">제한이 반환 된의 크기 (바이트)입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="8a277-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a277-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="8a277-113">Return Value</span></span>  

 <span data-ttu-id="8a277-114">`S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="8a277-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a277-115">설명</span><span class="sxs-lookup"><span data-stu-id="8a277-115">Remarks</span></span>  

 <span data-ttu-id="8a277-116">이 메서드는 [ICLRStrongName:: GetHashFromFileW](iclrstrongname-gethashfromfilew-method.md) 메서드와 동일 합니다. 단, 파일 이름 사양은 유니코드가 아니라 ANSI입니다.</span><span class="sxs-lookup"><span data-stu-id="8a277-116">This method is the same as the [ICLRStrongName::GetHashFromFileW](iclrstrongname-gethashfromfilew-method.md) method, except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a277-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a277-117">Requirements</span></span>  

 <span data-ttu-id="8a277-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a277-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a277-119">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="8a277-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8a277-120">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a277-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a277-121">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a277-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a277-122">참조</span><span class="sxs-lookup"><span data-stu-id="8a277-122">See also</span></span>

- [<span data-ttu-id="8a277-123">GetHashFromFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="8a277-123">GetHashFromFileW Method</span></span>](iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="8a277-124">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a277-124">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
