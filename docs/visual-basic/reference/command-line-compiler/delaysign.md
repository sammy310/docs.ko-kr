---
description: '자세한 정보: -delaysign'
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: fc3e52f63431da870355e369e6ffeb8b7b14c5ab
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100461504"
---
# <a name="-delaysign"></a>-delaysign

어셈블리를 완전히 서명할지, 아니면 부분적으로 서명할지를 지정합니다.

## <a name="syntax"></a>구문

```console
-delaysign[+ | -]
```

## <a name="arguments"></a>인수

`+` &#124; `-`  
선택 사항입니다. 어셈블리에 완전히 서명하려면 `-delaysign-`를 사용하고 어셈블리에 공개 키를 배치하고 서명된 해시의 공간을 예약하려면 `-delaysign+`을 사용합니다. 기본값은 `-delaysign-`입니다.

## <a name="remarks"></a>설명

`-delaysign` 옵션은 [-keyfile](keyfile.md) 또는 [-keycontainer](keycontainer.md)와 함께 사용하지 않으면 효과가 없습니다.

완전히 서명된 어셈블리를 요청할 경우 컴파일러는 매니페스트(어셈블리 메타데이터)가 포함된 파일을 해시하고 프라이빗 키로 해당 해시에 서명합니다. 결과로 생성되는 디지털 서명은 매니페스트가 포함된 파일에 저장됩니다. 어셈블리 서명이 연기된 경우 컴파일러는 서명을 컴퓨팅하거나 저장하지 않고 나중에 서명을 추가할 수 있도록 파일에 공간을 예약합니다.

예를 들어 조직의 개발자는 `-delaysign+`을 사용하여 테스터가 글로벌 어셈블리 캐시에 등록하고 사용할 수 있는 어셈블리의 서명되지 않은 테스트 버전을 배포할 수 있습니다. 어셈블리에 대한 작업이 완료되면 조직의 프라이빗 키를 담당하는 사람이 어셈블리에 완전히 서명할 수 있습니다. 이 구획화는 조직의 프라이빗 키가 공개되지 않도록 보호하는 동시에 모든 개발자가 어셈블리 작업을 수행할 수 있도록 합니다.

어셈블리 서명에 대한 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../../../standard/assembly/create-use-strong-named.md)을 참조하세요.

### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a>Visual Studio 통합 개발 환경에서 -delaysign을 설정하려면 다음을 수행합니다.

1. **솔루션 탐색기** 에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성** 을 클릭합니다.

2. **시그니처** 탭을 클릭합니다.

3. **지연 서명만** 상자에서 값을 설정합니다.

## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [-keyfile](keyfile.md)
- [-keycontainer](keycontainer.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
