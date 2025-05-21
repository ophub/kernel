From 59d66d6c9465f4fee9c8fc6acc4235be9342baff Mon Sep 17 00:00:00 2001
From: xxx <68696949+xxx@users.noreply.github.com>
Date: Wed, 21 May 2025 12:15:46 +0800
Subject: [PATCH] fix i2cA and i2cB miossing pins

---
 arch/arm64/boot/dts/amlogic/meson-gxbb.dtsi | 4 ++++
 1 file changed, 4 insertions(+)

diff --git a/arch/arm64/boot/dts/amlogic/meson-gxbb.dtsi b/arch/arm64/boot/dts/amlogic/meson-gxbb.dtsi
index 256c46771d..2a8d05373e 100644
--- a/arch/arm64/boot/dts/amlogic/meson-gxbb.dtsi
+++ b/arch/arm64/boot/dts/amlogic/meson-gxbb.dtsi
@@ -333,6 +333,8 @@
 
 &i2c_A {
 	clocks = <&clkc CLKID_I2C>;
+	pinctrl-names = "default";
+	pinctrl-0 = <&i2c_a_pins>;
 };
 
 &i2c_AO {
@@ -341,6 +343,8 @@
 
 &i2c_B {
 	clocks = <&clkc CLKID_I2C>;
+	pinctrl-names = "default";
+	pinctrl-0 = <&i2c_b_pins>;
 };
 
 &i2c_C {
