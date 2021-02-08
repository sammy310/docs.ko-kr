---
description: '자세히 알아보기: ISymUnmanagedBinder:: GetReaderForFile 메서드'
title: ISymUnmanagedBinder::GetReaderForFile 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderForFile
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderForFile
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderForFile method [.NET Framework debugging]
- GetReaderForFile method [.NET Framework debugging]
ms.assetid: 46c06258-831e-47c8-a50a-8650af6b637e
topic_type:
- apiref
ms.openlocfilehash: ede494cbc1bbe4059b98a639c1d0621dc2cbdfa6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790219"
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="d3104-103">ISymUnmanagedBinder::GetReaderForFile 메서드</span><span class="sxs-lookup"><span data-stu-id="d3104-103">ISymUnmanagedBinder::GetReaderForFile Method</span></span>

<span data-ttu-id="d3104-104">메타 데이터 인터페이스와 파일 이름이 지정 된 경우 모듈에 연결 된 디버깅 기호를 읽을 올바른 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 인터페이스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3104-104">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="d3104-105">이 메서드는 실행 파일 옆에 있는 경우에만 PDB (프로그램 데이터베이스) 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d3104-105">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="d3104-106">이러한 변경은 보안상의 목적으로 수행 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d3104-106">This change has been made for security purposes.</span></span> <span data-ttu-id="d3104-107">PDB 파일을 더 광범위 하 게 검색 해야 하는 경우 [ISymUnmanagedBinder2:: GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3104-107">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3104-108">구문</span><span class="sxs-lookup"><span data-stu-id="d3104-108">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3104-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d3104-109">Parameters</span></span>  

 `importer`  
 <span data-ttu-id="d3104-110">진행 메타 데이터 가져오기 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d3104-110">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="d3104-111">진행 파일 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d3104-111">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="d3104-112">진행 검색 경로에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d3104-112">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="d3104-113">제한이 반환 된 [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface로 설정 된 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d3104-113">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3104-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="d3104-114">Return Value</span></span>  

 <span data-ttu-id="d3104-115">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d3104-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3104-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d3104-116">Requirements</span></span>  

 <span data-ttu-id="d3104-117">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="d3104-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3104-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3104-118">See also</span></span>

- [<span data-ttu-id="d3104-119">ISymUnmanagedBinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3104-119">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="d3104-120">GetReaderForFile2 메서드</span><span class="sxs-lookup"><span data-stu-id="d3104-120">GetReaderForFile2 Method</span></span>](isymunmanagedbinder2-getreaderforfile2-method.md)
