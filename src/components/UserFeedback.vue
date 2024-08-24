<template>
    <div>
        <div class="feedback-card card">
            <div class="card-header">
                <a href="" class="close-btn" @click="closeModal(false)">X</a>
                <h3>User Feedback</h3>
            </div>
            <div class="card-body">
                <div class="mb-3">
                    <label for="type" class="">
                        <span class="is-required">*</span>
                        類別
                    </label>
                    <!-- <input type="text" class="form-control" id="type" placeholder="請選擇類別"> -->

                    <select class="form-select" aria-label="Type select">
                        <option selected> </option>
                        <option value="1">操作問題</option>
                        <option value="2">優化建議</option>
                        <option value="3">Bug反饋</option>
                        <option value="4">其他</option>
                    </select>
                </div>
                <div class="mb-3">
                    <label for="title" class="">
                        <span class="is-required">*</span>
                        標題
                        <small>(限30字內)</small>
                    </label>
                    <input type="text" class="form-control" id="title" placeholder="請輸入標題">
                </div>
                <div class="mb-3">
                    <label for="describe" class="">
                        <span class="is-required">*</span>
                        描述
                        <small>(限300字內)</small>
                    </label>
                    <input type="text" class="form-control" id="describe" placeholder="請描述你的意見/問題">
                </div>
                <div class="mb-3">
                    <label for="formFileLg" class="">
                        參考圖片
                        <small>(僅支援PNG、JPG格式，每張5MB內)</small>
                    </label>
                    <input class="form-control form-control-lg" id="formFileLg" type="file">
                    <p>可提供意見/問題截圖(上傳數量 0/3)</p>
                </div>

            </div>
            <div class="card-footer">
                <button class="btn btn-primary" @click="closeModal(false)">Submit</button>
            </div>
        </div>

    </div>
</template>

<script>
export default {
    name: 'UserFeedback',
    data() {
        return {

        }
    },
    props: {
        modelType: Boolean
    },
    mounted() { },
    methods: {
        closeModal(state) {
            this.$emit('close-modal', state);
        },
    },

}
</script>

<style scoped>
.feedback-card {
    width: 70%;
    height: 80%;
    margin: auto;
    background-color: white;
    position: relative;
}

.is-required {
    color: red;
    font-size: 1rem;
    margin-left: 5px;
}

.close-btn {
    position: absolute;
    top: 10px;
    right: 10px;
    font-size: 24px;
    cursor: pointer;
    color: #000;
}

.card-body {
    text-align: start;
}
</style>