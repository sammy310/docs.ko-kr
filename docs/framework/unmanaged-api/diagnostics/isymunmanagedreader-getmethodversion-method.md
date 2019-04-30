---
title: ISymUnmanagedReader::GetMethodVersion 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b5d4145e6c76cf95f2468a3f5ad59edcd310423e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993319"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="1f77d-102">ISymUnmanagedReader::GetMethodVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="1f77d-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="1f77d-103">메서드 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1f77d-103">Gets the method version.</span></span> <span data-ttu-id="1f77d-104">메서드 버전 1에서 시작 하 고 메서드가 다시 컴파일될 때마다 증분됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f77d-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="1f77d-105">메서드를 변경 하지 않고 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f77d-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f77d-106">구문</span><span class="sxs-lookup"><span data-stu-id="1f77d-106">Syntax</span></span>  
  
```  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f77d-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1f77d-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="1f77d-108">[in] 버전을 가져올 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="1f77d-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="1f77d-109">[out] 메서드 버전을 수신 하는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1f77d-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f77d-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="1f77d-110">Return Value</span></span>  
 <span data-ttu-id="1f77d-111">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="1f77d-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f77d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1f77d-112">Requirements</span></span>  
 <span data-ttu-id="1f77d-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1f77d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f77d-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="1f77d-114">See also</span></span>

- [<span data-ttu-id="1f77d-115">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1f77d-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
