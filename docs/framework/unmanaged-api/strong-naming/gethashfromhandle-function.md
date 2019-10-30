---
title: GetHashFromHandle 함수
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
ms.openlocfilehash: dc241324f5844610d7b86b7cb9668f84d4525395
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140658"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="76ae3-102">GetHashFromHandle 함수</span><span class="sxs-lookup"><span data-stu-id="76ae3-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="76ae3-103">지정된 해시 알고리즘을 사용하여 지정된 파일 핸들로 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="76ae3-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="76ae3-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76ae3-104">This function has been deprecated.</span></span> <span data-ttu-id="76ae3-105">대신 [ICLRStrongName:: GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ae3-105">Use the [ICLRStrongName::GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76ae3-106">구문</span><span class="sxs-lookup"><span data-stu-id="76ae3-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76ae3-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="76ae3-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="76ae3-108">진행 해시할 파일의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="76ae3-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="76ae3-109">[in, out] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="76ae3-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="76ae3-110">기본 알고리즘에는 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ae3-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="76ae3-111">제한이 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="76ae3-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="76ae3-112">진행 `pbHash`요청 된 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="76ae3-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="76ae3-113">제한이 반환 된 `pbHash`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="76ae3-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76ae3-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="76ae3-114">Requirements</span></span>  
 <span data-ttu-id="76ae3-115">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76ae3-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76ae3-116">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="76ae3-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="76ae3-117">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76ae3-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="76ae3-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76ae3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76ae3-119">참조</span><span class="sxs-lookup"><span data-stu-id="76ae3-119">See also</span></span>

- [<span data-ttu-id="76ae3-120">GetHashFromHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="76ae3-120">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="76ae3-121">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76ae3-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
