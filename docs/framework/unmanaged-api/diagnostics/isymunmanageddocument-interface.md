---
title: ISymUnmanagedDocument 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument
helpviewer_keywords:
- ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type:
- apiref
ms.openlocfilehash: a8ff6d3a925773e58e0713a87b167420c246f85b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615568"
---
# <a name="isymunmanageddocument-interface"></a>ISymUnmanagedDocument 인터페이스
기호 저장소가 참조하는 문서를 나타냅니다. 문서는 URL (uniform resource locator) 및 문서 유형 GUID로 정의 됩니다. URL 및 문서 유형 GUID를 사용 하 여 문서를 저장 하는 방법에 관계 없이 문서를 찾을 수 있습니다. 문서 원본을 기호 저장소에 저장 하 고이 인터페이스를 통해 검색할 수 있습니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[FindClosestLine 메서드](isymunmanageddocument-findclosestline-method.md)|이 문서에서 시퀀스 위치가 될 수도 있고 그렇지 않을 수도 있는 줄을 지정 하 여 시퀀스 위치인 가장 가까운 줄을 반환 합니다.|  
|[GetCheckSum 메서드](isymunmanageddocument-getchecksum-method.md)|체크섬을 가져옵니다.|  
|[GetCheckSumAlgorithmId 메서드](isymunmanageddocument-getchecksumalgorithmid-method.md)|체크섬 알고리즘 식별자를 가져오거나, 체크섬이 없을 경우 모든 0의 GUID를 반환 합니다.|  
|[GetDocumentType 메서드](isymunmanageddocument-getdocumenttype-method.md)|이 문서의 문서 유형을 가져옵니다.|  
|[GetLanguage 메서드](isymunmanageddocument-getlanguage-method.md)|이 문서의 언어 식별자를 가져옵니다.|  
|[GetLanguageVendor 메서드](isymunmanageddocument-getlanguagevendor-method.md)|이 문서의 언어 공급 업체를 가져옵니다.|  
|[GetSourceLength 메서드](isymunmanageddocument-getsourcelength-method.md)|포함 리소스의 길이(바이트)를 가져옵니다.|  
|[GetSourceRange 메서드](isymunmanageddocument-getsourcerange-method.md)|포함 된 소스의 지정 된 범위를 지정 된 버퍼에 반환 합니다.|  
|[GetURL 메서드](isymunmanageddocument-geturl-method.md)|이 문서에 대 한 URL을 반환 합니다.|  
|[HasEmbeddedSource 메서드](isymunmanageddocument-hasembeddedsource-method.md)|`true`문서에 디버깅 기호에 포함 된 소스가 있으면를 반환 하 고, 그렇지 않으면를 반환 `false` 합니다.|  
  
## <a name="see-also"></a>참고 항목

- [진단 기호 저장소 인터페이스](diagnostics-symbol-store-interfaces.md)
