---
title: ISymUnmanagedBinder2::GetReaderForFile2 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2.GetReaderForFile2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2
helpviewer_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2 method [.NET Framework debugging]
- GetReaderForFile2 method [.NET Framework debugging]
ms.assetid: dd92dcaf-403c-464d-a254-21594985dddd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: db917820de92b2e347385afc5217c0ca190825cd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776840"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a><span data-ttu-id="4ba63-102">ISymUnmanagedBinder2::GetReaderForFile2 메서드</span><span class="sxs-lookup"><span data-stu-id="4ba63-102">ISymUnmanagedBinder2::GetReaderForFile2 Method</span></span>
<span data-ttu-id="4ba63-103">지정 된 메타 데이터 인터페이스 및 파일 이름을 올바른 반환 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 모듈과 관련 디버깅 기호를 읽는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba63-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="4ba63-104">이 메서드는 보다는 프로그램 데이터베이스 (PDB) 파일에 대 한 보다 광범위 한 검색을 제공 합니다 [isymunmanagedbinder:: Getreaderforfile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="4ba63-104">This method provides a more extensive search for the program database (PDB) file than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ba63-105">구문</span><span class="sxs-lookup"><span data-stu-id="4ba63-105">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ba63-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4ba63-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="4ba63-107">[in] 메타 데이터 가져오기 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba63-107">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="4ba63-108">[in] 파일 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba63-108">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="4ba63-109">[in] 검색 경로에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba63-109">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="4ba63-110">[in] 값을 [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) 기호 판독기를 검색할 때 사용 되는 정책을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba63-110">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="4ba63-111">[out] 설정 된 포인터를 반환 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba63-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ba63-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="4ba63-112">Return Value</span></span>  
 <span data-ttu-id="4ba63-113">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba63-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ba63-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4ba63-114">Requirements</span></span>  
 <span data-ttu-id="4ba63-115">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4ba63-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ba63-116">설명</span><span class="sxs-lookup"><span data-stu-id="4ba63-116">Remarks</span></span>  
 <span data-ttu-id="4ba63-117">이 버전의 메서드는 모듈 옆에 있는 오른쪽 이외의 영역에서 PDB 파일을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba63-117">This version of the method can search for the PDB file in areas other than right next to the module.</span></span> <span data-ttu-id="4ba63-118">검색 정책을 결합 하 여 제어할 수 있습니다 [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba63-118">The search policy can be controlled by combining [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span></span> <span data-ttu-id="4ba63-119">예를 들어 `AllowReferencePathAccess | AllowSymbolServerAccess` pdb 기호 서버에서 실행 파일 옆에 있는 한 있지만 하거나 하지 않는 레지스트리 쿼리 실행 파일의 경로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba63-119">For example, `AllowReferencePathAccess | AllowSymbolServerAccess` looks for the PDB next to the executable file and on a symbol server, but does not query the registry or use the path in the executable file.</span></span> <span data-ttu-id="4ba63-120">경우는 `searchPath` 매개 변수를 제공, 해당 디렉터리 항상 검색 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ba63-120">If the `searchPath` parameter is provided, those directories will always be searched.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ba63-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="4ba63-121">See also</span></span>

- [<span data-ttu-id="4ba63-122">ISymUnmanagedBinder2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ba63-122">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="4ba63-123">GetReaderForFile 메서드</span><span class="sxs-lookup"><span data-stu-id="4ba63-123">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
