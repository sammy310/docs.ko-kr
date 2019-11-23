---
title: ISymUnmanagedWriter::SetSymAttribute 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type:
- apiref
ms.openlocfilehash: 8a4d205586921b377147eeab80754e1a0d9e52b0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427848"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="2dd41-102">ISymUnmanagedWriter::SetSymAttribute 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd41-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="2dd41-103">Defines a custom attribute based upon its name.</span><span class="sxs-lookup"><span data-stu-id="2dd41-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="2dd41-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span><span class="sxs-lookup"><span data-stu-id="2dd41-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dd41-105">구문</span><span class="sxs-lookup"><span data-stu-id="2dd41-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2dd41-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2dd41-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="2dd41-107">[in] The metadata token for which the attribute is being defined.</span><span class="sxs-lookup"><span data-stu-id="2dd41-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="2dd41-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span><span class="sxs-lookup"><span data-stu-id="2dd41-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="2dd41-109">[in] A `ULONG32` that indicates the size of the `data` array.</span><span class="sxs-lookup"><span data-stu-id="2dd41-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="2dd41-110">[in] The attribute value.</span><span class="sxs-lookup"><span data-stu-id="2dd41-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2dd41-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="2dd41-111">Return Value</span></span>  
 <span data-ttu-id="2dd41-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="2dd41-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dd41-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2dd41-113">Requirements</span></span>  
 <span data-ttu-id="2dd41-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2dd41-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dd41-115">참조</span><span class="sxs-lookup"><span data-stu-id="2dd41-115">See also</span></span>

- [<span data-ttu-id="2dd41-116">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2dd41-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
