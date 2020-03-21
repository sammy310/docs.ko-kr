---
title: '방법: 이미지 메타데이터 읽기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
ms.openlocfilehash: e2b56175e625281a920c390e5feb4238e3cb7f44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182518"
---
# <a name="how-to-read-image-metadata"></a>방법: 이미지 메타데이터 읽기

일부 이미지 파일에는 이미지의 기능을 결정하기 위해 읽을 수 있는 메타데이터가 포함되어 있습니다. 예를 들어 디지털 사진에는 이미지를 캡처하는 데 사용되는 카메라의 확인 및 모델을 결정하기 위해 읽을 수 있는 메타데이터가 포함될 수 있습니다. GDI+를 사용하면 기존 메타데이터를 읽을 수 있으며 이미지 파일에 새 메타데이터를 쓸 수도 있습니다.

GDI+는 개체에 개별 메타데이터를 저장합니다. <xref:System.Drawing.Imaging.PropertyItem> <xref:System.Drawing.Image> 개체의 <xref:System.Drawing.Image.PropertyItems%2A> 속성을 읽고 파일에서 모든 메타데이터를 검색할 수 있습니다. 속성은 <xref:System.Drawing.Image.PropertyItems%2A> 개체의 <xref:System.Drawing.Imaging.PropertyItem> 배열을 반환합니다.

<xref:System.Drawing.Imaging.PropertyItem> 개체에는 다음과 같은 네 `Id` `Value`가지 `Len`속성이 있습니다. `Type`

## <a name="id"></a>Id

메타데이터 항목을 식별하는 태그입니다. 할당할 수 있는 <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 일부 값은 다음 표에 표시됩니다.

|16 진수 값|Description|
|-----------------------|-----------------|
|0x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|이미지 제목<br /><br /> 장비 제조업체<br /><br /> 장비 모델<br /><br /> 엑시프티오리지널<br /><br /> 노출 시간 엑시프<br /><br /> 휘도 테이블<br /><br /> 크로도도 테이블|

## <a name="value"></a>값

값의 배열입니다. 값의 형식은 속성에 <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 의해 결정됩니다.

## <a name="len"></a>Len

<xref:System.Drawing.Imaging.PropertyItem.Value%2A> 속성이 가리키는 값 배열의 길이(바이트)입니다.

## <a name="type"></a>Type

속성이 가리키는 배열의 값의 데이터 `Value` 형식입니다. `Type` 속성 값으로 표시된 형식은 다음 표에 표시됩니다.

|숫자 값|Description|
|-------------------|-----------------|
|1|`Byte`|
|2|ASCII로 인코딩된 개체의 `Byte` 배열|
|3|16비트 정수|
|4|32비트 정수|
|5|합리적인 숫자를 `Byte` 나타내는 두 개체의 배열|
|6|사용되지 않음|
|7|정의되지 않음|
|8|사용되지 않음|
|9|`SLong`|
|10|`SRational`|

## <a name="example"></a>예제
  
다음 코드 예제에서는 파일에 `FakePhoto.jpg`7개의 메타데이터를 읽고 표시합니다. 목록의 두 번째 (인덱스 1) <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 속성 항목에는 0x010F(장비 제조업체) 및 <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2(ASCII 인코딩된 바이트 배열)가 있습니다. 코드 예제에는 해당 속성 항목의 값이 표시됩니다.

[!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
[!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]

코드는 다음과 유사한 출력을 생성합니다.

```output
 Property Item 0
  
 id: 0x320
  
 type: 2

 length: 16 bytes
  
 Property Item 1
  
 id: 0x10f
  
 type: 2
  
 length: 17 bytes
  
 Property Item 2
  
 id: 0x110
  
 type: 2
  
 length: 7 bytes
  
 Property Item 3
  
 id: 0x9003
  
 type: 2
  
 length: 20 bytes
  
 Property Item 4
  
 id: 0x829a
  
 type: 5
  
 length: 8 bytes
  
 Property Item 5
  
 id: 0x5090
  
 type: 3
  
 length: 128 bytes
  
 Property Item 6
  
 id: 0x5091
  
 type: 3
  
 length: 128 bytes
  
 The equipment make is Northwind Camera.
 ```

## <a name="compiling-the-code"></a>코드 컴파일

앞의 예제는 Windows Forms와 함께 사용하도록 <xref:System.Windows.Forms.PaintEventArgs> `e`설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 이 요구사항입니다. 폼의 <xref:System.Windows.Forms.Control.Paint> 이벤트를 처리하고 이 코드를 페인트 이벤트 처리기에 붙여넣습니다. 시스템에서 유효한 `FakePhoto.jpg` 이미지 이름과 경로로 바꾸고 네임스페이스를 `System.Drawing.Imaging` 가져와야 합니다.

## <a name="see-also"></a>참고 항목

- [이미지, 비트맵 및 메타파일](images-bitmaps-and-metafiles.md)
- [이미지, 비트맵, 아이콘 및 메타파일 사용](working-with-images-bitmaps-icons-and-metafiles.md)
