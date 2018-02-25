<template>
    <Menu :theme="menuTheme" :active-name="activeMenuName" :open-names="openNames">
        <template v-for="item in menuList">
            <Submenu :name="item.name" :key="item.name">
                <template slot="title">
                    <Icon :type="item.icon"></Icon>
                    <span>{{ item.title }}</span>
                </template>
                <template v-for="child in item.children">
                    <MenuItem :name="child.name" :key="'menuitem' + child.name">
                        {{ child.title }}
                    </MenuItem>
                </template>
            </Submenu>
        </template>
    </Menu>
</template>
<script>
    export default {
        name: 'SideBarMenu',
        props: {
            menuList: Array,
            activeMenuName: String,
            menuTheme: {
                type: String,
                default: 'dark'
            },
            openNames: Array
        },
        data () {
            return {
            }
        }
    }
</script>
