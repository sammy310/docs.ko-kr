---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: 770dcad385c522a548a0c6fd3b6ef02dfbac82f5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61649714"
---
# <a name="-delaysign"></a>-delaysign
어셈블리를 완전히 서명할지, 아니면 부분적으로 서명할지를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-delaysign[+ | -]  
```  
  
## <a name="arguments"></a>인수  
 `+` &#124; `-`  
 선택 사항입니다. 어셈블리에 완전히 서명하려면 `-delaysign-`를 사용하고 사용 하 여 `-delaysign+` 부호 있는 해시에 대 한 어셈블리 및 예약 공간에 공개 키를 저장 하려는 경우. 기본값은 `-delaysign-`입니다.  
  
## <a name="remarks"></a>설명  
 합니다 `-delaysign` 옵션은 사용 하지 않는 한 효과가 없습니다 [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) 하거나 [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)합니다.  
  
 완전히 서명된 어셈블리를 요청할 경우 컴파일러는 매니페스트(어셈블리 메타데이터)가 포함된 파일을 해시하고 개인 키로 해당 해시에 서명합니다. 결과로 생성되는 디지털 서명은 매니페스트가 포함된 파일에 저장됩니다. 어셈블리 서명이 연기 되 면 컴파일러 계산 하거나 나중에 서명을 추가할 수 있도록 파일에 서명 하지만 예약 공간을 저장 하지 않습니다.  
  
 사용 하 여 예를 들어 `-delaysign+`, 조직에서 개발자 테스터가 어셈블리를 전역 어셈블리 캐시를 사용 하 여 등록 하 고 사용할 수 있는 어셈블리의 서명 되지 않은 테스트 버전을 배포할 수 있습니다. 어셈블리에 대 한 작업 완료 되 면 담당자는 조직의 개인 키를 어셈블리에 완전히 서명할 수 있습니다. 이 작업은 모든 개발자는 어셈블리의 작업을 허용 하는 동안 공개에서 조직의 개인 키를 보호 합니다.  
  
 참조 [강력한 어셈블리 만들기 및 사용](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) 어셈블리 서명에 대 한 자세한 내용은 합니다.  
  
### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a>Visual Studio 통합된 개발 환경에서-delaysign을 설정 하려면  
  
1. **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다.   
  
2. **시그니처** 탭을 클릭합니다.  
  
3. 값을 설정 합니다 **서명만 연기** 상자입니다.  
  
## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
