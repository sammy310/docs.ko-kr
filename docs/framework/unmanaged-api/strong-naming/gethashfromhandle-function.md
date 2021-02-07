---
description: '자세히 알아보기: GetHashFromHandle 함수'
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
ms.openlocfilehash: 5951a5befd9e66b13a3b3033398614fca1f1a9d8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736553"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="4c2ee-103">GetHashFromHandle 함수</span><span class="sxs-lookup"><span data-stu-id="4c2ee-103">GetHashFromHandle Function</span></span>

<span data-ttu-id="4c2ee-104">지정된 해시 알고리즘을 사용하여 지정된 파일 핸들로 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-104">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="4c2ee-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-105">This function has been deprecated.</span></span> <span data-ttu-id="4c2ee-106">대신 [ICLRStrongName:: GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-106">Use the [ICLRStrongName::GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c2ee-107">구문</span><span class="sxs-lookup"><span data-stu-id="4c2ee-107">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c2ee-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4c2ee-108">Parameters</span></span>  

 `hFile`  
 <span data-ttu-id="4c2ee-109">진행 해시할 파일의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-109">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="4c2ee-110">[in, out] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="4c2ee-111">기본 알고리즘에는 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-111">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="4c2ee-112">제한이 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-112">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="4c2ee-113">진행 요청 된 최대 크기 `pbHash` 입니다.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-113">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="4c2ee-114">제한이 반환 된의 크기 (바이트)입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="4c2ee-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c2ee-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4c2ee-115">Requirements</span></span>  

 <span data-ttu-id="4c2ee-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c2ee-117">**헤더:** StrongName</span><span class="sxs-lookup"><span data-stu-id="4c2ee-117">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="4c2ee-118">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4c2ee-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c2ee-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c2ee-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c2ee-120">See also</span></span>

- [<span data-ttu-id="4c2ee-121">GetHashFromHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="4c2ee-121">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="4c2ee-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4c2ee-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
