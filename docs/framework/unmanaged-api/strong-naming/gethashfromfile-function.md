---
title: GetHashFromFile 함수
ms.date: 03/30/2017
api_name:
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
ms.openlocfilehash: ea2b70f37668587fb02513ab54da6c1915e2918d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176983"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="3f4db-102">GetHashFromFile 함수</span><span class="sxs-lookup"><span data-stu-id="3f4db-102">GetHashFromFile Function</span></span>
<span data-ttu-id="3f4db-103">지정된 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4db-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="3f4db-104">이 함수는 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4db-104">This function has been deprecated.</span></span> <span data-ttu-id="3f4db-105">대신 [ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4db-105">Use the [ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f4db-106">구문</span><span class="sxs-lookup"><span data-stu-id="3f4db-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f4db-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3f4db-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="3f4db-108">【인】 해시할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3f4db-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="3f4db-109">【인, 아웃】 해시를 생성할 때 사용할 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="3f4db-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="3f4db-110">유효한 알고리즘은 Win32 CryptoAPI에 의해 정의된 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="3f4db-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="3f4db-111">0으로 설정된 경우 `piHashAlg` 기본 알고리즘 CALG_SHA-1이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f4db-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="3f4db-112">【아웃】 생성된 해시를 포함하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3f4db-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="3f4db-113">【인】 `pbHash` 가리키는 버퍼의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="3f4db-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="3f4db-114">【아웃】 반환된 `pbHash`의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="3f4db-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f4db-115">설명</span><span class="sxs-lookup"><span data-stu-id="3f4db-115">Remarks</span></span>  
 <span data-ttu-id="3f4db-116">이 함수는 파일 이름 사양이 유니코드 대신 ANSI라는 점을 제외하면 [GetHashFromFileW와](gethashfromfilew-function.md)동일합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4db-116">This function is the same as [GetHashFromFileW](gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f4db-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f4db-117">Requirements</span></span>  
 <span data-ttu-id="3f4db-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f4db-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f4db-119">**헤더:** 스트롱네임</span><span class="sxs-lookup"><span data-stu-id="3f4db-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="3f4db-120">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3f4db-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3f4db-121">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f4db-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f4db-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f4db-122">See also</span></span>

- [<span data-ttu-id="3f4db-123">GetHashFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="3f4db-123">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="3f4db-124">GetHashFromFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="3f4db-124">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="3f4db-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f4db-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
