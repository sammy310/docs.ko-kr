---
description: '자세히 알아보기: BC36810: 프로젝트에서 XML 스키마를 컴파일하는 동안 오류가 발생 했습니다.'
title: 프로젝트에서 XML 스키마를 컴파일하는 동안 오류가 발생했습니다.
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 78e88208c0d3df12e7bad8ab46b1d91bce559923
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796485"
---
# <a name="bc36810-errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a>BC36810: 프로젝트에서 XML 스키마를 컴파일하는 동안 오류가 발생 했습니다.

프로젝트에서 XML 스키마를 컴파일하는 동안 오류가 발생 했습니다. 따라서 XML IntelliSense를 사용할 수 없습니다.

 프로젝트에 포함 된 XSD (XML 스키마 정의) 스키마에 오류가 있습니다. 이 오류는 프로젝트에 대 한 기존 XSD 스키마 집합과 충돌 하는 XSD 스키마 (.xsd) 파일을 추가 하는 경우에 발생 합니다.

 **오류 ID:** BC36810

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- **오류 목록** 창에서 해당 경고를 두 번 클릭 합니다. Visual Basic는 XSD 파일에서 경고 소스인 위치로 이동 합니다. XSD 스키마의 오류를 수정 하십시오.

- 필요한 모든 XSD 스키마 (.xsd) 파일이 프로젝트에 포함 되어 있는지 확인 합니다. **솔루션 탐색기** 에서 .xsd 파일을 보려면 [ **프로젝트** ] 메뉴에서 [ **모든 파일 표시** ]를 클릭 해야 할 수도 있습니다. .Xsd 파일을 마우스 오른쪽 단추로 클릭 한 다음 **프로젝트에 포함** 을 클릭 하 여 프로젝트에 파일을 포함 합니다.

- XML to Schema 마법사를 사용 하는 경우 동일한 소스에서 두 번 이상 스키마를 유추 하는 경우이 오류가 발생할 수 있습니다. 이 경우 프로젝트에서 기존 XSD 스키마 파일을 제거 하 고 스키마 항목 템플릿에 새 XML을 추가한 다음 프로젝트에 적용 가능한 모든 XML 원본을 사용 하 여 XML 스키마 마법사를 제공할 수 있습니다.

- XSD 스키마에서 오류가 식별 되지 않으면 XML 컴파일러에 자세한 오류 메시지를 제공 하는 데 충분 한 정보가 없을 수 있습니다. 프로젝트에 포함 된 .xsd 파일에 대 한 XML 네임 스페이스가 Visual Studio의 XML 스키마 집합에 대해 식별 된 xml 네임 스페이스와 일치 하는지 확인 하는 경우 자세한 오류 정보를 볼 수 있습니다.

## <a name="see-also"></a>참고 항목

- [오류 목록 창](/visualstudio/ide/reference/error-list-window)
- [XML](../../programming-guide/language-features/xml/index.md)
