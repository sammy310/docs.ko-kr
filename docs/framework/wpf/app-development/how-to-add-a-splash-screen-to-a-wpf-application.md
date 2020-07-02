---
title: 시작 화면을 추가 하는 방법
description: 시작 창 또는 시작 화면을 Windows Presentation Foundation (WPF) 응용 프로그램에 추가 하는 방법을 알아봅니다.
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 0d0cf2e2a550320650c3b4a0c257071a0403c32b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617962"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a>방법: WPF 애플리케이션에 시작 화면 추가

이 항목에서는 시작 창 또는 *시작 화면*을 WINDOWS PRESENTATION FOUNDATION (WPF) 응용 프로그램에 추가 하는 방법을 보여 줍니다.

## <a name="to-add-an-existing-image-as-a-splash-screen"></a>기존 이미지를 시작 화면으로 추가 하려면

1. 시작 화면에 사용할 이미지를 만들거나 찾습니다. WIC (Windows Imaging Component)에서 지 원하는 모든 이미지 형식을 사용할 수 있습니다. 예를 들어 BMP, GIF, JPEG, PNG 또는 TIFF 형식을 사용할 수 있습니다.

2. WPF 응용 프로그램 프로젝트에 이미지 파일을 추가 합니다.

3. **솔루션 탐색기**에서 이미지를 선택 합니다.

4. 속성 창에서 **빌드 작업** 속성의 드롭다운 화살표를 클릭 합니다.

5. 드롭다운 목록에서 **SplashScreen** 를 선택 합니다.

6. **F5** 키를 눌러 응용 프로그램을 빌드하고 실행 합니다.

     시작 화면 이미지가 화면 가운데에 표시 되 고 주 응용 프로그램 창이 표시 되 면 페이드 인 됩니다.

## <a name="to-exclude-the-splash-screen-from-build"></a>빌드에서 시작 화면을 제외 하려면

1. **솔루션 탐색기**에서 시작 화면 이미지를 선택 합니다.

2. **속성** 창에서 **빌드 작업** 을 **없음**으로 설정 합니다.

## <a name="to-remove-the-splash-screen-from-an-application"></a>응용 프로그램에서 시작 화면을 제거 하려면

**솔루션 탐색기**에서 시작 화면 이미지를 삭제 합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.SplashScreen>
- [방법: 프로젝트에 기존 항목 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))
