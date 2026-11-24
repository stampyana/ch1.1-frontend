
<template>
  <q-page padding>
    <div class="text-h4 q-mb-md">
      Version Control + Docker Demo (Quasar)
    </div>

    <!-- Git Workflow -->
    <q-card class="q-mb-md">
      <q-card-section>
        <div class="text-h6">
          Git Workflow (ตัวอย่างขั้นตอนทำงาน)
        </div>

        <q-list bordered separator class="q-mt-sm">
          <q-item
            v-for="(step, index) in gitSteps"
            :key="index"
          >
            <q-item-section avatar>
              <q-badge>{{ index + 1 }}</q-badge>
            </q-item-section>

            <q-item-section>
              <q-item-label>{{ step.title }}</q-item-label>
              <q-item-label caption>
                {{ step.detail }}
              </q-item-label>
            </q-item-section>
          </q-item>
        </q-list>
      </q-card-section>
    </q-card>

    <!-- Docker Concepts -->
    <q-card>
      <q-card-section>
        <div class="text-h6">
          Docker Concepts (สรุปสั้น ๆ)
        </div>

        <q-list bordered separator class="q-mt-sm">
          <q-item
            v-for="(item, index) in dockerItems"
            :key="index"
          >
            <q-item-section>
              <q-item-label>{{ item.title }}</q-item-label>
              <q-item-label caption>
                {{ item.detail }}
              </q-item-label>
            </q-item-section>
          </q-item>
        </q-list>
      </q-card-section>
    </q-card>
  </q-page>
</template>

<script setup>
const gitSteps = [
  {
    title: 'แก้โค้ด Quasar ใน src/',
    detail: 'เพิ่มหน้า / component ใหม่ เช่น IndexPage.vue, Layout ต่าง ๆ',
  },
  {
    title: 'ตรวจสอบสถานะไฟล์',
    detail: 'ใช้คำสั่ง git status ดูว่าไฟล์ไหนเปลี่ยนแปลงบ้าง',
  },
  {
    title: 'เพิ่มไฟล์เข้า staging',
    detail: 'ใช้ git add เพื่อเตรียมไฟล์ก่อนบันทึก',
  },
  {
    title: 'สร้าง commit พร้อมข้อความแบบ Conventional Commits',
    detail: 'เช่น feat: add Git workflow demo page',
  },
  {
    title: 'push ขึ้น GitHub',
    detail: 'ใช้ git push -u origin feature/quasar-demo แล้วเปิด Pull Request',
  },
]

const dockerItems = [
  {
    title: 'Image',
    detail: 'แพ็กเกจที่มีไฟล์และการตั้งค่าที่ใช้สร้าง Container',
  },
  {
    title: 'Container',
    detail: 'ตัวที่สร้างจาก Image และกำลังรันโปรแกรมอยู่',
  },
  {
    title: 'Volume',
    detail: 'ใช้เก็บข้อมูลให้คงอยู่ แม้ Container จะถูกลบ',
  },
  {
    title: 'Network',
    detail: 'ช่วยให้บริการต่าง ๆ ใน Docker ติดต่อสื่อสารกันได้',
  },
]
</script>
