---
title: ISymUnmanagedNamespace::GetName 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetName
helpviewer_keywords:
- ISymUnmanagedNamespace::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 657bf91d-005a-4ea4-9298-04d1291c0bc3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9017eeaf8e80c3dc0b546c1f3c2fb54634b3e949
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939518"
---
# <a name="isymunmanagednamespacegetname-method"></a><span data-ttu-id="18751-102">ISymUnmanagedNamespace::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="18751-102">ISymUnmanagedNamespace::GetName Method</span></span>
<span data-ttu-id="18751-103">이 네임 스페이스의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="18751-103">Gets the name of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18751-104">구문</span><span class="sxs-lookup"><span data-stu-id="18751-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18751-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18751-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="18751-106">[in] A `ULONG32` 의 크기를 나타내는 `szName` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="18751-106">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="18751-107">[out] 에 대 한 포인터를 `ULONG32` 문자의 null 종결을 포함 하는 네임 스페이스 이름 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="18751-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespace name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="18751-108">[out] 네임 스페이스 이름을 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="18751-108">[out] A pointer to a buffer that contains the namespace name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18751-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="18751-109">Return Value</span></span>  
 <span data-ttu-id="18751-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="18751-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18751-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18751-111">Requirements</span></span>  
 <span data-ttu-id="18751-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="18751-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18751-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="18751-113">See also</span></span>

- [<span data-ttu-id="18751-114">ISymUnmanagedNamespace 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18751-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
