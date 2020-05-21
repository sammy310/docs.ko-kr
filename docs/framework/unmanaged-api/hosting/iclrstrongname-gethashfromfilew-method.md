---
title: ICLRStrongName::GetHashFromFileW 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
ms.openlocfilehash: 6dbb3360132186c38c007fb5fa12a3724ca145aa
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762099"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="900b5-102">ICLRStrongName::GetHashFromFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="900b5-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="900b5-103">유니코드 문자열로 지정된 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="900b5-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="900b5-104">구문</span><span class="sxs-lookup"><span data-stu-id="900b5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="900b5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="900b5-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="900b5-106">진행 해시할 파일의 유니코드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="900b5-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="900b5-107">[in, out] 해시를 생성할 때 사용할 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="900b5-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="900b5-108">유효한 알고리즘은 Win32 CryptoAPI에서 정의 되는 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="900b5-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="900b5-109">`piHashAlg`가 0으로 설정 되 면 기본 알고리즘 CALG_SHA-1이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="900b5-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="900b5-110">제한이 생성 된 해시를 포함 하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="900b5-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="900b5-111">진행 가 가리키는 버퍼의 최대 크기입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="900b5-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="900b5-112">제한이 의 크기 (바이트)입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="900b5-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="900b5-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="900b5-113">Return Value</span></span>  
 <span data-ttu-id="900b5-114">`S_OK`메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="900b5-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="900b5-115">설명</span><span class="sxs-lookup"><span data-stu-id="900b5-115">Remarks</span></span>  
 <span data-ttu-id="900b5-116">이 메서드는 [ICLRStrongName:: GetHashFromFile](iclrstrongname-gethashfromfile-method.md) 메서드와 동일 합니다. 단, 파일 이름 사양은 ANSI 대신 유니코드입니다.</span><span class="sxs-lookup"><span data-stu-id="900b5-116">This method is the same as the [ICLRStrongName::GetHashFromFile](iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="900b5-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="900b5-117">Requirements</span></span>  
 <span data-ttu-id="900b5-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="900b5-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="900b5-119">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="900b5-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="900b5-120">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="900b5-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="900b5-121">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="900b5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="900b5-122">참조</span><span class="sxs-lookup"><span data-stu-id="900b5-122">See also</span></span>

- [<span data-ttu-id="900b5-123">GetHashFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="900b5-123">GetHashFromFile Method</span></span>](iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="900b5-124">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="900b5-124">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
