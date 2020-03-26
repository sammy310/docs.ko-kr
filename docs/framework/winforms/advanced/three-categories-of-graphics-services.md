---
title: 세 가지 범주의 그래픽 서비스
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: fa7391ef0f7170ddb9d9d24aa5a1a03635bf46e0
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291735"
---
# <a name="three-categories-of-graphics-services"></a>세 가지 범주의 그래픽 서비스
Windows Forms의 그래픽 제품은 다음과 같은 세 가지 광범위한 범주에 속합니다.  
  
- 2차원(2차원) 벡터 그래픽  
  
- 이미징  
  
- 입력 체계  
  
## <a name="2d-vector-graphics"></a>2D 벡터 그래픽  
 선, 곡선 및 그림과 같은 2차원 벡터 그래픽은 좌표계의 점 집합에 의해 지정된 기본 요소입니다. 예를 들어 직선은 두 끝점에 의해 지정되고 사각형은 왼쪽 위 모서리의 위치를 지정하는 점과 너비와 높이를 주는 숫자 쌍으로 지정됩니다. 단순 패스는 직선으로 연결된 점의 배열에 의해 지정됩니다. 베지어 스플래라인은 4개의 컨트롤 포인트로 지정된 정교한 곡선입니다.  
  
 GDI+는 프리미티브 자체에 대한 정보를 저장하는 클래스및 구조, 기본 요소를 그리는 방법에 대한 정보를 저장하는 클래스 및 실제로 도면을 수행하는 클래스를 제공합니다. 예를 들어, <xref:System.Drawing.Rectangle> 구조는 사각형의 위치와 크기를 저장합니다. 클래스는 <xref:System.Drawing.Pen> 선 색상, 선 너비 및 선 스타일에 대한 정보를 저장합니다. <xref:System.Drawing.Graphics> 클래스에는 선, 사각형, 패스 및 기타 그림을 그리는 메서드가 있습니다. 닫힌 그림과 <xref:System.Drawing.Brush> 패스가 색상이나 패턴으로 채워지는 방법에 대한 정보를 저장하는 여러 클래스도 있습니다.  
  
 그래픽 명령 시퀀스인 벡터 이미지를 메타파일로 기록할 수 있습니다. GDI+는 <xref:System.Drawing.Imaging.Metafile> 메타파일을 기록, 표시 및 저장하기 위한 클래스를 제공합니다. <xref:System.Drawing.Imaging.MetafileHeader> 및 <xref:System.Drawing.Imaging.MetaHeader> 클래스를 사용하여 메타파일 헤더에 저장된 데이터를 검사할 수 있습니다.  
  
## <a name="imaging"></a>이미징  
 특정 종류의 사진은 벡터 그래픽 기술로 표시하기가 어렵거나 불가능합니다. 예를 들어 도구 모음 단추의 그림과 아이콘으로 표시되는 그림은 선과 곡선의 컬렉션으로 지정하기 어렵습니다. 붐비는 야구장의 고해상도 디지털 사진은 벡터 기술로 제작하기가 훨씬 더 어렵습니다. 이 유형의 이미지는 비트맵으로 저장되며, 이 배열은 화면에서 개별 점의 색상을 나타내는 숫자 배열입니다. GDI+는 <xref:System.Drawing.Bitmap> 비트맵을 표시, 조작 및 저장하기 위한 클래스를 제공합니다.  
  
## <a name="typography"></a>입력 체계  
 타이포그래피는 다양한 글꼴, 크기 및 스타일로 텍스트를 표시하는 것입니다. GDI+는 이 복잡한 작업에 대한 광범위한 지원을 제공합니다. GDI+의 새로운 기능 중 하나는 LCD 화면에서 렌더링된 텍스트를 더 매끄러운 모양으로 만드는 서브픽셀 안티앨리어싱입니다.  
  
 또한 Windows Forms는 <xref:System.Windows.Forms.TextRenderer> 동급에서 GDI 기능이 있는 텍스트를 그리는 옵션을 제공합니다.  
  
## <a name="see-also"></a>참조

- [그래픽 개요](graphics-overview-windows-forms.md)
- [GDI+ 관리 코드 정보](about-gdi-managed-code.md)
- [관리형 그래픽 클래스 사용](using-managed-graphics-classes.md)
