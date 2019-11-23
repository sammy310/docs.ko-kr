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
ms.openlocfilehash: fcaf748413321f684336543e60f735af69894b51
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436004"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="60e22-102">ISymUnmanagedReader::GetMethodVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="60e22-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="60e22-103">Gets the method version.</span><span class="sxs-lookup"><span data-stu-id="60e22-103">Gets the method version.</span></span> <span data-ttu-id="60e22-104">The method version starts at 1 and is incremented each time the method is recompiled.</span><span class="sxs-lookup"><span data-stu-id="60e22-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="60e22-105">Recompilation can happen without changes to the method.</span><span class="sxs-lookup"><span data-stu-id="60e22-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60e22-106">구문</span><span class="sxs-lookup"><span data-stu-id="60e22-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60e22-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="60e22-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="60e22-108">[in] The method for which to get the version.</span><span class="sxs-lookup"><span data-stu-id="60e22-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="60e22-109">[out] A pointer to a variable that receives the method version.</span><span class="sxs-lookup"><span data-stu-id="60e22-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60e22-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="60e22-110">Return Value</span></span>  
 <span data-ttu-id="60e22-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="60e22-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60e22-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="60e22-112">Requirements</span></span>  
 <span data-ttu-id="60e22-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="60e22-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60e22-114">참조</span><span class="sxs-lookup"><span data-stu-id="60e22-114">See also</span></span>

- [<span data-ttu-id="60e22-115">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60e22-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
