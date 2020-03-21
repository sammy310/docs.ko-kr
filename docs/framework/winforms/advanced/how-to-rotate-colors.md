---
title: '방법: 색 회전'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 8d2717dd7b819e963126072279b361fda02188bc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111337"
---
# <a name="how-to-rotate-colors"></a>방법: 색 회전
4차원 색상 공간에서의 회전은 시각화하기 어렵습니다. 색상 구성 요소 중 하나를 고정된 상태로 유지하는 데 동의하여 회전을 보다 쉽게 시각화할 수 있습니다. 알파 구성 요소를 1(완전히 불투명)으로 고정하는 데 동의한다고 가정합니다. 그런 다음 그림과 같이 빨간색, 녹색 및 파란색 축으로 3차원 색상 공간을 시각화할 수 있습니다.  
  
 ![빨간색, 녹색 및 파란색 축으로 회전을 보여 주는 그림입니다.](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 색상은 3D 공간의 포인트로 생각할 수 있습니다. 예를 들어 공간의 점(1, 0, 0)은 빨간색을 나타내고 공간의 점(0, 1, 0)은 녹색을 나타냅니다.  
  
 다음 그림에서는 빨간색-녹색 평면에서 60도 각도로 색상(1, 0, 0)을 회전하는 것이 무엇을 의미하는지 보여 주시다. 적색-녹색 평면과 평행한 평면의 회전은 파란색 축에 대한 회전으로 생각할 수 있습니다.  
  
 ![파란색 축에 대한 회전을 보여 주는 그림입니다.](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 다음 그림에서는 세 좌표 축(빨간색, 녹색, 파란색)에 대한 회전을 수행하기 위해 색상 행렬을 초기화하는 방법을 보여 주며 다음과 같은 방법을 보여 주며 다음과 같은 방법을 보여 주시면 됩니다.  
  
 ![색상 행렬을 초기화하여 세 축에 대한 회전을 수행합니다.](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a>예제  
 다음 예제에서는 하나의 색상(1, 0, 0.6)인 이미지를 가져와 파란색 축에 대해 60도 회전을 적용합니다. 회전 각도는 적색-녹색 평면과 평행한 평면에서 스윕됩니다.  
  
 다음 그림에서는 왼쪽의 원본 이미지와 오른쪽의 색상 회전 이미지를 보여 주며 있습니다.  
  
 ![원본 이미지와 색상 회전 이미지를 보여 주는 그림입니다.](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 다음 그림에서는 다음 코드에서 수행되는 색상 회전의 시각화를 보여 주며 다음과 같은 그림이 보여 주며 다음과 같은 코드에서 수행됩니다.
  
 ![색상 회전의 시각화를 보여 주는 그림입니다.](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows Forms와 함께 사용하도록 <xref:System.Windows.Forms.PaintEventArgs> `e`설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 이 요구사항입니다. 시스템에서 `RotationInput.bmp` 유효한 이미지 파일 이름 및 경로로 바꿉니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Windows Forms의 그래픽 및 그리기](graphics-and-drawing-in-windows-forms.md)
- [이미지 다시 칠하기](recoloring-images.md)
