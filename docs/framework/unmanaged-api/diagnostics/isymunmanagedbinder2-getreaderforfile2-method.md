---
description: '자세히 알아보기: ISymUnmanagedBinder2:: GetReaderForFile2 메서드'
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
ms.openlocfilehash: c1a180ceec07c3087150613365acfce646adc34e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689939"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a><span data-ttu-id="6ad77-103">ISymUnmanagedBinder2::GetReaderForFile2 메서드</span><span class="sxs-lookup"><span data-stu-id="6ad77-103">ISymUnmanagedBinder2::GetReaderForFile2 Method</span></span>

<span data-ttu-id="6ad77-104">메타 데이터 인터페이스와 파일 이름이 지정 된 경우 모듈에 연결 된 디버깅 기호를 읽을 올바른 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 인터페이스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad77-104">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="6ad77-105">이 메서드는 [ISymUnmanagedBinder:: GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) 메서드 보다 더 광범위 한 PDB (프로그램 데이터베이스) 파일 검색을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad77-105">This method provides a more extensive search for the program database (PDB) file than the [ISymUnmanagedBinder::GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ad77-106">구문</span><span class="sxs-lookup"><span data-stu-id="6ad77-106">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ad77-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6ad77-107">Parameters</span></span>  

 `importer`  
 <span data-ttu-id="6ad77-108">진행 메타 데이터 가져오기 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6ad77-108">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="6ad77-109">진행 파일 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6ad77-109">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="6ad77-110">진행 검색 경로에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6ad77-110">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="6ad77-111">진행 기호 판독기를 검색할 때 사용할 정책을 지정 하는 [Corsymsearchpolicyattributes](corsymsearchpolicyattributes-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6ad77-111">[in] A value of the [CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="6ad77-112">제한이 반환 된 [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface로 설정 된 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6ad77-112">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ad77-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="6ad77-113">Return Value</span></span>  

 <span data-ttu-id="6ad77-114">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="6ad77-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ad77-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ad77-115">Requirements</span></span>  

 <span data-ttu-id="6ad77-116">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="6ad77-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ad77-117">설명</span><span class="sxs-lookup"><span data-stu-id="6ad77-117">Remarks</span></span>  

 <span data-ttu-id="6ad77-118">이 버전의 메서드는 모듈 바로 옆의 영역에서 PDB 파일을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad77-118">This version of the method can search for the PDB file in areas other than right next to the module.</span></span> <span data-ttu-id="6ad77-119">[Corsymsearchpolicyattributes](corsymsearchpolicyattributes-enumeration.md)를 결합 하 여 검색 정책을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad77-119">The search policy can be controlled by combining [CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md).</span></span> <span data-ttu-id="6ad77-120">예를 들어은 `AllowReferencePathAccess | AllowSymbolServerAccess` 실행 파일 및 기호 서버 옆에 있는 PDB를 찾지만 레지스트리를 쿼리하거나 실행 파일의 경로를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad77-120">For example, `AllowReferencePathAccess | AllowSymbolServerAccess` looks for the PDB next to the executable file and on a symbol server, but does not query the registry or use the path in the executable file.</span></span> <span data-ttu-id="6ad77-121">`searchPath`매개 변수가 제공 되는 경우 해당 디렉터리는 항상 검색 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ad77-121">If the `searchPath` parameter is provided, those directories will always be searched.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ad77-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ad77-122">See also</span></span>

- [<span data-ttu-id="6ad77-123">ISymUnmanagedBinder2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6ad77-123">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="6ad77-124">GetReaderForFile 메서드</span><span class="sxs-lookup"><span data-stu-id="6ad77-124">GetReaderForFile Method</span></span>](isymunmanagedbinder-getreaderforfile-method.md)
