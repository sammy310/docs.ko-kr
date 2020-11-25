---
title: ImportFile2 메서드
ms.date: 03/30/2017
api_name:
- IALink.ImportFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile2
helpviewer_keywords:
- ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type:
- apiref
ms.openlocfilehash: d02bc53676dd5afb0222a1ea366a8f2bd1f94f62
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705230"
---
# <a name="importfile2-method"></a><span data-ttu-id="5417d-102">ImportFile2 메서드</span><span class="sxs-lookup"><span data-stu-id="5417d-102">ImportFile2 Method</span></span>

<span data-ttu-id="5417d-103">어셈블리 및 바인딩되지 않은 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5417d-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="5417d-104">이 메서드는 [Importfile 메서드와](importfile-method.md)유사 하지만, 가져오는 파일이 디스크에 존재 하지 않는 경우에도 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5417d-104">This method is like [ImportFile Method](importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5417d-105">구문</span><span class="sxs-lookup"><span data-stu-id="5417d-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportFile2(  
    LPCWSTR         pszFilename,  
    LPCWSTR         pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL            fSmartImport,  
    mdToken*        pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD*          pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5417d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5417d-106">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="5417d-107">가져올 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5417d-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="5417d-108">어셈블리에 연결 된 파일의 이름을 바꾸는 데 사용할 수 있는 선택적 출력 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5417d-108">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="5417d-109">선택적 범위 [IMetaDataAssemblyImport interface](../metadata/imetadataassemblyimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5417d-109">Optional scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="5417d-110">TRUE 이면 ImportTypes를 사용 합니다. 그렇지 않으면 가져오기는 수동으로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5417d-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="5417d-111">파일이 나 어셈블리에 대 한 ID를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5417d-111">Receives the ID for the file or assembly.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="5417d-112">[IMetaDataAssemblyImport 인터페이스](../metadata/imetadataassemblyimport-interface.md) 인터페이스를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="5417d-112">Receives the [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="5417d-113">파일이 어셈블리가 아닌 경우 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="5417d-113">NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="5417d-114">가져온 파일 및/또는 범위를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="5417d-114">Receives the found of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5417d-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="5417d-115">Return Value</span></span>  

 <span data-ttu-id="5417d-116">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5417d-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5417d-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5417d-117">Requirements</span></span>  

 <span data-ttu-id="5417d-118">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5417d-118">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5417d-119">참조</span><span class="sxs-lookup"><span data-stu-id="5417d-119">See also</span></span>

- [<span data-ttu-id="5417d-120">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5417d-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="5417d-121">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5417d-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="5417d-122">ALink API</span><span class="sxs-lookup"><span data-stu-id="5417d-122">ALink API</span></span>](index.md)
