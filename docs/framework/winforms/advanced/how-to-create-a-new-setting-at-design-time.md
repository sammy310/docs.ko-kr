---
title: '방법: 디자인 타임에 새 설정 만들기'
description: Visual Studio의 설정 디자이너를 사용 하 여 디자인 타임에 새 Windows Forms 설정을 만드는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: ce37b42191999e29de2f2f7f7e7abfa0ec3f4d47
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325846"
---
# <a name="how-to-create-a-new-setting-at-design-time"></a>방법: 디자인 타임에 새 설정 만들기

디자인 타임에 Visual Studio의 설정 디자이너를 사용 하 여 새 설정을 만들 수 있습니다. 설정 디자이너는 새 설정을 만들고 이러한 설정에 대 한 속성을 지정할 수 있는 그리드 스타일 인터페이스입니다. 새 설정의 이름, 값, 유형 및 범위를 지정 해야 합니다. 설정이 만들어지면 코드에서 액세스할 수 있습니다.

## <a name="create-a-new-setting-at-design-time-in-c"></a>C에서 디자인 타임에 새 설정 만들기\#

1. Visual Studio를 엽니다.

2. **솔루션 탐색기**에서 프로젝트의 **속성** 노드를 확장 합니다.

3. 새 설정을 추가할 settings 파일을 두 번 클릭 합니다. 이 파일의 기본 이름은 Settings입니다.

4. 설정 디자이너에서 설정의 **이름**, **값**, **유형**및 **범위** 를 설정 합니다. 각 행은 단일 설정을 나타냅니다.

## <a name="create-a-new-setting-at-design-time-in-visual-basic"></a>디자인 타임에 Visual Basic에 새 설정 만들기

1. Visual Studio를 엽니다.

2. **솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 합니다.

3. **속성** 페이지에서 **설정** 탭을 선택 합니다.

4. 설정 디자이너에서 설정의 **이름**, **값**, **유형**및 **범위** 를 설정 합니다. 각 행은 단일 설정을 나타냅니다.

## <a name="see-also"></a>참조

- [애플리케이션 설정 및 사용자 설정 사용](using-application-settings-and-user-settings.md)
- [애플리케이션 설정 개요](application-settings-overview.md)
- [방법: 디자인 타임에 기존 설정 값 변경](how-to-change-the-value-of-an-existing-setting-at-design-time.md)
