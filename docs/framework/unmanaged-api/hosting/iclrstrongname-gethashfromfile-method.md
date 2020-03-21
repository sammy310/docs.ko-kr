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
ms.openlocfilehash: ed735c3d7830551581df35793f3f6fdc4953dc8c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178070"
---
# <a name="iclrstrongnamegethashfromfile-method"></a><span data-ttu-id="99042-102">ICLRStrongName::GetHashFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="99042-102">ICLRStrongName::GetHashFromFile Method</span></span>
<span data-ttu-id="99042-103">지정된 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="99042-103">Generates a hash over the contents of the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99042-104">구문</span><span class="sxs-lookup"><span data-stu-id="99042-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99042-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="99042-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="99042-106">【인】 해시할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="99042-106">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="99042-107">【인, 아웃】 해시를 생성할 때 사용할 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="99042-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="99042-108">유효한 알고리즘은 Win32 CryptoAPI에 의해 정의된 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="99042-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="99042-109">0으로 설정된 경우 `piHashAlg` 기본 알고리즘 CALG_SHA-1이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="99042-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="99042-110">【아웃】 생성된 해시를 포함하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="99042-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="99042-111">【인】 `pbHash` 가리키는 버퍼의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="99042-111">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="99042-112">【아웃】 반환된 `pbHash`의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="99042-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99042-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="99042-113">Return Value</span></span>  
 <span data-ttu-id="99042-114">`S_OK`메서드가 성공적으로 완료된 경우 그렇지 않으면 실패를 나타내는 HRESULT 값입니다(목록의 [공통 HRESULT 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="99042-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99042-115">설명</span><span class="sxs-lookup"><span data-stu-id="99042-115">Remarks</span></span>  
 <span data-ttu-id="99042-116">이 메서드는 [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) 메서드와 동일 하지만 파일 이름 사양유니코드 대신 ANSI입니다.</span><span class="sxs-lookup"><span data-stu-id="99042-116">This method is the same as the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method, except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99042-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99042-117">Requirements</span></span>  
 <span data-ttu-id="99042-118">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99042-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99042-119">**헤더:** 메타호스트</span><span class="sxs-lookup"><span data-stu-id="99042-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="99042-120">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="99042-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99042-121">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99042-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99042-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99042-122">See also</span></span>

- [<span data-ttu-id="99042-123">GetHashFromFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="99042-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="99042-124">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99042-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
