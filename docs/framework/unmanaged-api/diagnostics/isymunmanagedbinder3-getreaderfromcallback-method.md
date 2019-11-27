---
title: ISymUnmanagedBinder3::GetReaderFromCallback 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3.GetReaderFromCallback
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3::GetReaderFromCallback
helpviewer_keywords:
- GetReaderFromCallback method [.NET Framework debugging]
- ISymUnmanagedBinder3::GetReaderFromCallback method [.NET Framework debugging]
ms.assetid: 4ef83bd2-3d8e-499e-8a12-d9d6fd6ced30
topic_type:
- apiref
ms.openlocfilehash: a0cccc0adfc666cc8e373bc1f89c8f6f97068fde
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449306"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a><span data-ttu-id="e5aa7-102">ISymUnmanagedBinder3::GetReaderFromCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="e5aa7-102">ISymUnmanagedBinder3::GetReaderFromCallback Method</span></span>
<span data-ttu-id="e5aa7-103">사용자가 `IID_IDiaReadExeAtRVACallback` 또는 `IID_IDiaReadExeAtOffsetCallback` 콜백을 통해 구현 하거나 제공 하 여 메모리에서 디버그 디렉터리 정보를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5aa7-103">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the debug directory information from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5aa7-104">구문</span><span class="sxs-lookup"><span data-stu-id="e5aa7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5aa7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e5aa7-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="e5aa7-106">진행 메타 데이터 가져오기 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e5aa7-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="e5aa7-107">진행 파일 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e5aa7-107">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="e5aa7-108">진행 검색 경로에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e5aa7-108">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="e5aa7-109">진행 기호 판독기를 검색할 때 사용할 정책을 지정 하는 [Corsymsearchpolicyattributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e5aa7-109">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `callback`  
 <span data-ttu-id="e5aa7-110">진행 콜백 함수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e5aa7-110">[in] A pointer to the callback function.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="e5aa7-111">제한이 반환 된 [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface로 설정 된 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e5aa7-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5aa7-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="e5aa7-112">Return Value</span></span>  
 <span data-ttu-id="e5aa7-113">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e5aa7-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5aa7-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5aa7-114">Requirements</span></span>  
 <span data-ttu-id="e5aa7-115">**헤더:** CorSym</span><span class="sxs-lookup"><span data-stu-id="e5aa7-115">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5aa7-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5aa7-116">See also</span></span>

- [<span data-ttu-id="e5aa7-117">ISymUnmanagedBinder3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5aa7-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
